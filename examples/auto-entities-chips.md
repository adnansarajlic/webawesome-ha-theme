type: custom:auto-entities
card:
  type: custom:mushroom-chips-card
card_param: chips
filter:
  include:
    # 1. Batteri under 20% -> WebAwesome Warning
    - options:
        type: entity
        content_info: name
        card_mod:
          class: wa-chip-warning
      attributes:
        device_class: battery
      state: <20

    # 2. Rökdetektor "on" -> WebAwesome Danger
    - options:
        type: entity
        entity: this.entity_id
        content_info: name
        card_mod:
          class: wa-chip-danger
      attributes:
        device_class: smoke
      state: "on"

    # 3. Rökdetektor "unknown" -> WebAwesome Danger
    - options:
        type: entity
        entity: this.entity_id
        content_info: name
        card_mod:
          class: wa-chip-danger
      attributes:
        device_class: smoke
      state: unknown

    # 4. Vattenmätare >= 1 -> WebAwesome Info
    - options:
        type: entity
        entity: this.entity_id
        content_info: state
        card_mod:
          class: wa-chip-info
      entity_id:
        entity: sensor.watermeter_water_usage
        active_choice: entity
      state: ">=1"

    # 5. Sensor contact unknown -> WebAwesome Danger
    - options:
        card_mod:
          class: wa-chip-danger
      entity_id:
        custom: "*sensor_contact*"
        active_choice: custom
      state: unknown

    # 6. Lås domän -> WebAwesome Danger
    - options:
        type: entity
        entity: this.entity_id
        content_info: name
        card_mod:
          class: wa-chip-danger
      domain: lock

    # 7. Temperatur >= 66 -> WebAwesome Warning
    - options:
        type: entity
        entity: this.entity_id
        content_info: name
        card_mod:
          class: wa-chip-warning
      entity_id:
        custom: "*temperature*"
        active_choice: custom
      state: ">=66"

    # 8. Hall tvätt off -> WebAwesome Danger
    - options:
        type: entity
        entity: this.entity_id
        content_info: name
        card_mod:
          class: wa-chip-danger
      entity_id:
        entity: binary_sensor.hall_tvatt_sensor_contact
        active_choice: entity
      state: "off"

    # 9. Last seen unavailable -> WebAwesome Warning
    - options:
        type: entity
        entity: this.entity_id
        content_info: name
        card_mod:
          class: wa-chip-warning
      entity_id:
        custom: "*last_seen*"
        active_choice: custom
      state: unavailable

    # 10. Moisture on -> WebAwesome Info
    - options:
        type: entity
        entity: this.entity_id
        content_info: name
        card_mod:
          class: wa-chip-info
      attributes:
        device_class: moisture
      state: "on"

    # 11. Garageporten on -> WebAwesome Danger
    - options:
        type: entity
        entity: this.entity_id
        content_info: name
        card_mod:
          class: wa-chip-danger
      entity_id:
        custom: binary_sensor.garageporten_sensor_contact
        active_choice: custom
      state: "on"

    # 12. Niro battery <70 -> WebAwesome Danger
    - options:
        type: entity
        entity: this.entity_id
        content_info: name
        card_mod:
          class: wa-chip-danger
      entity_id:
        entity: sensor.niro_car_battery_level
        active_choice: entity
      state: <70

    # 13. Niro tire pressure on -> WebAwesome Danger
    - options:
        type: entity
        entity: this.entity_id
        content_info: name
        card_mod:
          class: wa-chip-danger
      entity_id:
        entity: binary_sensor.niro_tire_pressure_all
        active_choice: entity
      state: "on"

    # 14. Alla brandvarnare (Solid background) -> WebAwesome Danger Solid
    - options:
        type: entity
        entity: this.entity_id
        content_info: state
        card_mod:
          class: wa-chip-danger-solid
      entity_id:
        entity: binary_sensor.alla_brandvarnare
        active_choice: entity
      state: "on"

    # 15. Postnord -> WebAwesome Info
    - options:
        type: entity
        entity: this.entity_id
        content_info: state
        card_mod:
          class: wa-chip-info
      entity_id:
        entity: sensor.postnord_delivery_60580
        active_choice: entity
      state: "0"

    # 16. Vatten switch flow -> WebAwesome Info
    - options:
        type: entity
        entity: this.entity_id
        content_info: state
        card_mod:
          class: wa-chip-info
      entity_id:
        entity: sensor.vatten_switch_1_flow
        active_choice: entity
      state: ">0"

  exclude:
    - options: {}
      state: locked
    - options: {}
      entity_id:
        entity: binary_sensor.hall_tvatt_sensor_contact
        active_choice: entity
      state: "on"
    - options: {}
      entity_id:
        entity: camera.batterykamera
        active_choice: entity
      state: unavailable
unique: entity
sort:
  method: last_changed
  reverse: true
  count: 10
rename:
  type:
    - entity
    - device
  trim: false
  separator: " - "
