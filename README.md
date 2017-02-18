DHT11 Python library

This simple class can be used for reading temperature and humidity values from DHT11 sensor on Orange PI.

Usage

Instantiate the DHT11 class with the pin number as constructor parameter.
Call read() method, which will return DHT11Result object with actual values and error code.
For example:

from pyA20.gpio import gpio
from pyA20.gpio import port

# initialize GPIO
PIN2 = port.PA6
gpio.init()

# read data using pin port.PA6
instance = dht11.DHT11(pin=PIN2)
result = instance.read()

if result.is_valid():
    print("Temperature: %d C" % result.temperature)
    print("Humidity: %d %%" % result.humidity)
else:
    print("Error: %d" % result.error_code)

For working example, see dht11_example.py (you probably need to adjust pin for your configuration)
