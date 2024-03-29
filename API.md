# GPIO Expander Pi API

## `class GpioExpander`

Create an object `GpioExpander` to communicate with a particular board based on Amperka GPIO expander. The end-user libraries often wrap (or inherit) this class to provide domain-specific high level hardware interaction methods.

### `GpioExpander(i2c_address=42)`

Constructor. The `i2c_address` specifies the board I²C address which is `42` factory-default but can be changed programmatically.

### `pin_mode(pin: int, mode: PinMode) -> None`

Configures the operation `mode` of the `pin`:

- PinMode.INPUT
- PinMode.INPUT_PULLUP
- PinMode.INPUT_PULLDOWN
- PinMode.OUTPUT

### `analog_read(pin: int) -> float`

Reads a analog signal value from a pin of the board. Return value in range from `0.0` to `1.0`.

### `digital_read(pin: int) -> bool`

Reads a digital signal value from a pin of the board. Returns `True` or `False`.

### `digital_write(pin: int, value: bool) -> None`

Outputs digital signal (`True` or `False`) on a `pin`.

### `analog_write(pin: int, value: float) -> None`

Outputs PMW signal on a `pin`. The `value` argument specifies the duty cycle and should be in the range from `0.0` to `1.0`

### `change_address(new_address: int) -> None`

Changes the I²C address of the module. The change is in effect only while the board is powered on. If you want to save it permanently call the `save_address` method.

### `save_address() -> None`

Permanently saves the current board I²C address.

### `set_pwm_freq(freq: int) -> None`

Sets a PWM frequency (in hertz) for all PWM outputs of the GPIO expander. The `freq` argument should be in the range from `30` to `65535`.

### `reset() -> None`

Sets the board pins to the default state.
