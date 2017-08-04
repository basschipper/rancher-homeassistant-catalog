# OpenTherm Monitor

## Configure otmonitor

Example of the [otmonitor.conf](examples/otmonitor/otmonitor.conf) where:
- ${otgw.host} = your OTGW ip/host
- ${otgw.port} = your OTGW port
- ${mqtt.broker} = your MQTT (eg. Mosquitto) ip/host
- ${mqtt.port} = your MQTT port, eg. 1883
- ${mqtt.username} = your MQTT username 
- ${mqtt.password} = your MQTT password (base64 encoded)

## Configure Home Assistant

Sensor example:
```yaml
sensor:
  - platform: mqtt
    state_topic: "events/central_heating/otmonitor/roomtemperature"
    name: "OTGW Roomtemperature"
    unit_of_measurement: '°C'
  - platform: mqtt
    state_topic: "events/central_heating/otmonitor/boilerwatertemperature"
    name: "OTGW Boiler Water Temperature"
    unit_of_measurement: '°C'
```