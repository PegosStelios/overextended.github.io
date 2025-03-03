---
title: Methods
---

These functions are inherited from the [Vehicle class](../Server/).

## vehicle.set

Sets the vehicle's metadata for key to the given value.

```lua
vehicle.set(key, value)
```

- key: `string`
- value: `any`

## vehicle.get

Get a value from the vehicles's metadata, or omit the argument to get all metadata.

```lua
vehicle.get(key)
```

- key?: `string`

## vehicle.getState

Return the vehicle's statebag.

```lua
vehicle.getState()
```

## vehicle.getCoords

Return the vehicle's position.

```lua
vehicle.getCoords()
```

## vehicle.despawn

Despawns the vehicle but doesn't save it or update the stored value.

```lua
vehicle.despawn()
```

## vehicle.delete

Remove the vehicle from the database and despawns the entity.

```lua
vehicle.delete()
```

## vehicle.setStored

Updates the vehicle's "stored" value and optionally despawns it.

```lua
vehicle.setStored(value, despawn)
```

- value?: `string`
- despawn?: `boolean`

## vehicle.setOwner

Sets the vehicle's owner, matching a charid or nil to set it as unowned.

```lua
vehicle.setOwner(owner)
```

- owner?: `number`

## vehicle.setGroup

Sets the vehicle's group, which can be used for garage restrictions, unowned group vehicles, etc.

```lua
vehicle.setGroup(group)
```

- group?: `string`

## vehicle.setPlate

Sets the vehicle's plate, used in the database to ensure uniqueness. Does not necessarily match the plate property (i.e. fake plates).  
Plate is always formatted to 8 characters.

```lua
vehicle.setPlate(plate)
```

- plate: `string`
