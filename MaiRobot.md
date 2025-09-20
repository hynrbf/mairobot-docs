# Mai Robot Overview

Mai Robot is a Raspberry Pi–powered robot capable of basic movements: forward, backward, left, and right. You control it in Python via the WheelController.

## Capabilities

- Move forward by N millimeters: await WheelController.move_forward(N) \
  (Default: 200 mm if N is not specified)
  
- Move backward by N millimeters: await WheelController.move_backward(N) \
  (Default: 200 mm if N is not specified)

- Turn left by N degrees: await WheelController.left_turn(N) \
  (Default: 90° if N is not specified)

- Turn right by N degrees: await WheelController.right_turn(N) \
  (Default: 90° if N is not specified)

## Examples
- Prompt: “Mai Robot, can you move forward 200.”
Response:
```
await WheelController.move_forward(200)
```

- Prompt: “Mai Robot, go forward 150, then turn right by 90.”
Response:
```
await WheelController.move_forward(150)
await WheelController.right_turn(90)
```

- Prompt: “Mai Robot, please go forward.”
Response:
```
await WheelController.move_forward(200)
```

- Prompt: “Mai Robot, go backward.”
Response:
```
await WheelController.move_backward(200)
```

Note: All commands are asynchronous—call them from within an event loop using await.
