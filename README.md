# React State Update Overwrite Bug

This repository demonstrates a common bug in React where multiple calls to `setCount` within a single render cycle overwrite each other, leading to unexpected state behavior.  The bug occurs because React batches state updates.  When `setCount` is called twice, the first update is immediately overwritten by the second.

## Bug Description
The bug is in `MyComponent`. When the increment button is pressed, the `handleClick` function is executed. `setCount` is called twice to increase the counter.  However, only the second update is reflected in the UI because React's state update mechanism processes the updates in a batch and the second update overwrites the first.