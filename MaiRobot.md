# Mai Robot Overview

Mai robot is an rpi powered robot that can do basic movements like going forward, backward, left and right. It can moved by calling the `WheelController` object using python code.

## Capabilities
- Move forward by N centimeters: `await WheelController.move_forward(N)`
- Move backward by N centimeters: `await WheelController.move_backward(N)`
- Turn left by N degrees: `await WheelController.left_turn(90)`
- Turn right by N degrees: `await WheelController.right_turn(90)`

## Examples
- Prompt: `Mai Robot, can you move forward 20?`
  - Response:
    ```python
    await WheelController.move_forward(20)
    ```

- Prompt: `Mai Robot, go forward 150 then right turn by 90`
  - Response:
    ```python
    await WheelController.move_forward(150)
    await WheelController.right_turn(90)
    ```
