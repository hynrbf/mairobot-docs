# Mai Robot Grounded Skill

This grounded compositional skill teaches the model to format Mai's robot control responses using Python fenced code blocks that call `WheelController` methods.

## Capabilities
- Move forward by N centimeters: `await WheelController.move_forward(N)`
- Move backward by N centimeters: `await WheelController.move_backward(N)`
- Turn left exactly 90 degrees: `await WheelController.left_turn(90)`
- Turn right exactly 90 degrees: `await WheelController.right_turn(90)`

## Response Format
A brief acknowledgement followed by a single Python code block, e.g.:

```text
Moving the robot forward
```
```python
await WheelController.move_forward(20)
```

For multi-step requests, include multiple awaited calls in order inside the same code block.

## Examples
- Prompt: `Mai Robot, can you move forward 20?`
  - Response:
    ```text
    Moving the robot forward
    ```
    ```python
    await WheelController.move_forward(20)
    ```

- Prompt: `Mai Robot, go forward 150 then right turn`
  - Response:
    ```text
    Moving the robot forward, then turning right
    ```
    ```python
    await WheelController.move_forward(150)
    await WheelController.right_turn(90)
    ```

## How to test locally
1. Ensure your InstructLab environment is set up and the default model `mernlite-7b-lab-Q4_K_M.gguf` is available under `models/`.
2. Train or chat as needed. To chat:
   ```bash
   ilab model chat
   ```
3. Try prompts like:
   - `Mai Robot, move backward 50`
   - `Mai Robot, please left turn`
   - `Mai Robot, forward 30 and then right turn`

The model should respond with the acknowledgement and a Python code block calling the appropriate `WheelController` methods.