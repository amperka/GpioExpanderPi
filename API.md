# GPIO Expander Pi API

## `class GpioExpander`

Create an object `GpioExpander` to communicate with a particular board based on Amperka GPIO expander. The end-user libraries often wrap (or inherit) this class to provide domain-specific high level hardware interaction methods.

### `GpioExpander(i2c_address=42)`

Constructor. The `i2c_address` specifies the board I²C address which is `42` factory-default but can be changed programmatically.

### `pin_mode(pin: int, mode: int) -> None`

Configures the operation `mode` of the `pin`:

- GPIO.INPUT
- GPIO.INPUT_PULLUP
- GPIO.INPUT_PULLDOWN
- GPIO.OUTPUT

These constants are static members of the `GPIO` class.

### `analog_read(pin: int) -> float`

Reads the analog value from one pin of board. Return value in range from `0` to `1.0`.

### `digital_read(pin: int) -> bool`

Reads the bit value from one pin of board. Return `GPIO.HIGH` or `GPIO.LOW` value. This values defined as `True` and `False` respectively.

### `digital_write(pin: int, value: bool) -> None`

Write `GPIO.HIGH` or `GPIO.LOW` value to a `pin`. This values defined as `True` and `False` respectively.

### `analog_write(pin: int, value: float) -> None`

Writes an analog value from `0` to `1.0` (PWM wave) to a `pin`.

### `change_address(new_address: int) -> None`

Changes the I²C address of the module. The change is in effect only while the board is powered on. If you want to save it permanently call the `save_address` method.

### `save_address() -> None`

Permanently saves the current board I²C address.

### `pwm_freq(value: int) -> None`

Sets the PWM frequency for the analog output.

### `reset() -> None`

Sets the board pins to the default state.
