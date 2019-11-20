# GPIO Expander Pi API

## `class GpioExpander`

Create an object `GpioExpander` to communicate with a particular GpioExpander boards.

### `GpioExpander(i2c_address=42)`

The constructor for GpioExpander class. The `i2c_address` specifies the board
I²C address which is `42` factory-default but can be changed programmatically.

### `pin_mode(pin: int, value: int) -> None`

Configures state the `pin`:

- INPUT
- INPUT_PULLUP
- INPUT_PULLDOWN
- OUTPUT

### `analog_read(pin: int) -> float`

Reads the analog value from one pin of board. Return value in range from `0` to `1.0`.

### `digital_read(pin: int) -> int`

Reads the bit value from one pin of board. Return `0` or `1` value.

### `digital_write(pin: int) -> None`

Write `1` or `0` value to a `pin`.

### `analog_write(pin: int, value: int) -> None`

Writes an analog value from `0` to `255` (PWM wave) to a `pin`.

### `change_address(new_address: int) -> None`

Changes the I²C address of the module. The change is in effect only while the
board is powered on. If you want to save it permanently call the `save_address`
method.

### `save_address() -> None`

Permanently saves the current board I²C address.

### `pwm_freq(value: int) -> None`

Sets the PWM frequency for the analog output.

### `reset() -> None`

Sets the board pins to the default state.
