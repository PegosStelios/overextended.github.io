---
title: Server
sidebar_position: 1
---

## Ox.GetVehicle

Return an instance of CVehicle for the given entity.

```lua
local vehicle = Ox.GetVehicle(entity)
print(json.encode(vehicle, { indent = true }))
```

## Ox.GetVehicleFromNetId

Return an instance of CVehicle for the given entity, this time using it's netId.

```lua
local vehicle = Ox.GetVehicleFromNetId(netId)
print(json.encode(vehicle, { indent = true }))
```

## Ox.GetVehicles

Returns an array containing all vehicles. Methods will not be applied if the first argument is false.

```lua
local vehicles = Ox.GetVehicles(usemetatable)

for i = 1, #vehicles do
    local vehicle = vehicles[i]
    print(json.encode(vehicle, { indent = true }))
end
```

## Ox.CreateVehicle

Spawns a vehicle and returns the instance of CVehicle.  
If the first argument is a number, it will attempt to spawn a vehicle from the database with a matching id.

```lua
local vehicleId = MySQL.scalar.await('SELECT id FROM vehicles WHERE owner = ? LIMIT 1', { player.charid })

if vehicleId then
    local coords = player.getCoords()
    local vehicle = Ox.CreateVehicle(vehicleId, vector3(coords.x, coords.y + 1.0, coords.z) , GetEntityHeading(player.ped))

    if vehicle then
        print(json.encode(vehicle, { indent = true }))
    end
end
```

If the first argument is a table and the owner property is a number, or nil, the vehicle will be added to the database.  
Setting the owner as false creates a non-persistent vehicle.

```lua
local vehicle = Ox.CreateVehicle({
    model = 'sultanrs',
    owner = player.charid,
}, player.getCoords(), GetEntityHeading(player.ped))
```
