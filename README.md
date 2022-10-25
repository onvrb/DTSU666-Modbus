# Chint DTSU666-Modbus
Chint DTSU666-Modbus 3P4W Multifunction Power Analyzer with RS485 port Modbus-RTU plugin for [domoticz](https://www.domoticz.com/)

This is a fork from https://github.com/elfabriceu/DTSU666-Modbus

I assume that the original project was made for older DTSU666 models due to the original `pdf` publication in **2016**.
Since I have a DTSU666 manufactured in 2020, some values wer not working. I found this earlier **2019** `pdf` document which worked for my model. I suggest you try both projects and see which one works for you.

A standalone python script to send the data directly to InfluxDB can be found here: https://github.com/onvrb/Rail-Meter-TX

# Usage

- Go into into plugins folder in your domoticz (example `~/domoticz/plugins`)
- Clone the repo `git clone https://github.com/onvrb/DTSU666-Modbus`
- Start or restart your domoticz instance
- In your domoticz head out to `Hardware` and select `Chint DTSU666-Modbus`
- Default values should work. Debug will output all data to `Setup` > `Log` in domoticz. I suggest you try this and check that no errors occur.

# Dependencies

You don't need to install these modules unless you're doing some troubleshooting

Used python modules:
- [pyserial](https://pythonhosted.org/pyserial/)
- [minimalmodbus](http://minimalmodbus.readthedocs.io)


# Other useful info

Tested on the [docker container from linuxserver](https://hub.docker.com/r/linuxserver/domoticz) version `2022.1`.

To forward your RS485 adapter (assuming it's USB) to the container you can use the `--devices` flag or in a `docker compose`:
```yml
    devices:
      - /dev/ttyUSB0:/dev/ttyUSB0
```

Make sure you set it to the right port. If you just plugged it in, you can run `dmesg | tail`.
