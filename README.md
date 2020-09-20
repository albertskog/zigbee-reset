# Factory Reset Zigbee Device
This can be used to factory reset Zigbee lamps like Philips Hue with only a CC2531 dongle - no need for a hub or Hue remote. It uses Mosquitto and Zigbee2mqtt to send a [Touchlink factory reset](https://github.com/Koenkk/zigbee2mqtt.io/blob/develop/docs/information/touchlink.md).

## Requirements
* Docker
* Docker Compose
* Some way to publish a mqtt message, for example

    ``` 
    npm install mqtt -g
    ```

## Usage
* Replace `xxxxxxxxxxx` with your device's name in the last line of `docker-compose.yml`.

* Start the Docker containers with:

    ```
    docker-compose up
    ```

* Start Touchlink unpairing by publishing a an empty message to `zigbee2mqtt/bridge/config/touchlink/factory_reset`

    For example:

    ```
    mqtt pub -t "zigbee2mqtt/bridge/config/touchlink/factory_reset" -m ""
    ```

