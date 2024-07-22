#условные-выражения 

Если просто написали блок if, то подумайте, может вам стоит поставить и else. Одна из причин поставить else, это указать что else учтен или что будет если if не сработает.
Пример:
```rust
// Bad ❌
// Непонятно что если direction окажется None
if let Some(direction) = direction {
	road.target_lane = Self::get_lane_index(road.lanes_number, direction));

	if direction != TurnDirection::Forward {
		// Some very long code
		...
	}
}

// Good ✅
if let Some(direction) = direction {
	road.target_lane = Self::get_lane_index(road.lanes_number, direction));

	if direction != TurnDirection::Forward {
		// Some very long code
		...
	}
} else {
	// If no direction, set None for now
	road.target_lane = None;
}
```