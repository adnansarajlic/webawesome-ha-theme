type: custom:mushroom-chips-card
chips:
  - type: entity
    entity: person.adnan_sarajlic
    icon: mdi:account
    content_info: none
    use_entity_picture: true
    card_mod:
      style: |
        ha-card {
          --chip-background: {% if is_state('person.adnan_sarajlic', 'Hemma') or is_state('person.adnan_sarajlic', 'home') %} var(--wa-bg-success) {% else %} var(--wa-bg-danger) {% endif %};
          --chip-border-color: {% if is_state('person.adnan_sarajlic', 'Hemma') or is_state('person.adnan_sarajlic', 'home') %} var(--wa-success) {% else %} var(--wa-danger) {% endif %};
          --chip-border-width: 2px;
          --chip-font-size: 13px;
        }
        :host img {
          filter: {% if is_state('person.adnan_sarajlic', 'Hemma') or is_state('person.adnan_sarajlic', 'home') %} none {% else %} grayscale(100%) opacity(50%) {% endif %};
        }
  - type: entity
    entity: person.jasmina_sarajlic
    icon: mdi:account
    content_info: none
    use_entity_picture: true
    card_mod:
      style: |
        ha-card {
          --chip-background: {% if is_state('person.jasmina_sarajlic', 'Hemma') or is_state('person.jasmina_sarajlic', 'home') %} var(--wa-bg-success) {% else %} var(--wa-bg-danger) {% endif %};
          --chip-border-color: {% if is_state('person.jasmina_sarajlic', 'Hemma') or is_state('person.jasmina_sarajlic', 'home') %} var(--wa-success) {% else %} var(--wa-danger) {% endif %};
          --chip-border-width: 2px;
          --chip-font-size: 13px;
        }
        :host img {
          filter: {% if is_state('person.jasmina_sarajlic', 'Hemma') or is_state('person.jasmina_sarajlic', 'home') %} none {% else %} grayscale(100%) opacity(50%) {% endif %};
        }
  - type: entity
    entity: person.aidin
    icon: mdi:account
    content_info: none
    use_entity_picture: true
    tap_action:
      action: navigate
      navigation_path: "#aidin"
    card_mod:
      style: |
        ha-card {
          --chip-background: {% if is_state('person.aidin', 'Hemma') or is_state('person.aidin', 'home') %} var(--wa-bg-success) {% else %} var(--wa-bg-danger) {% endif %};
          --chip-border-color: {% if is_state('person.aidin', 'Hemma') or is_state('person.aidin', 'home') %} var(--wa-success) {% else %} var(--wa-danger) {% endif %};
          --chip-border-width: 2px;
          --chip-font-size: 13px;
        }
        :host img {
          filter: {% if is_state('person.aidin', 'Hemma') or is_state('person.aidin', 'home') %} none {% else %} grayscale(100%) opacity(50%) {% endif %};
        }
  - type: entity
    entity: person.ajla
    icon: mdi:account
    content_info: none
    use_entity_picture: true
    tap_action:
      action: navigate
      navigation_path: "#ajla"
    card_mod:
      style: |
        ha-card {
          --chip-background: {% if is_state('person.ajla', 'Hemma') or is_state('person.ajla', 'home') %} var(--wa-bg-success) {% else %} var(--wa-bg-danger) {% endif %};
          --chip-border-color: {% if is_state('person.ajla', 'Hemma') or is_state('person.ajla', 'home') %} var(--wa-success) {% else %} var(--wa-danger) {% endif %};
          --chip-border-width: 2px;
          --chip-font-size: 13px;
        }
        :host img {
          filter: {% if is_state('person.ajla', 'Hemma') or is_state('person.ajla', 'home') %} none {% else %} grayscale(100%) opacity(50%) {% endif %};
        }
  - type: entity
    entity: sensor.myrvagen_electricity_price
    content_info: state
    tap_action:
      action: navigate
      navigation_path: "#elpris"
    double_tap_action:
      action: navigate
      navigation_path: "#elpris"
    hold_action:
      action: navigate
      navigation_path: "#elpris"
    card_mod:
      style: |
        ha-card {
          --chip-background: {% set level = state_attr('sensor.myrvagen_electricity_price', 'current_level') %}
            {%- if level == 'VERY_CHEAP' or level == 'CHEAP' -%} var(--wa-bg-success)
            {%- elif level == 'NORMAL' -%} var(--wa-bg-info)
            {%- elif level == 'EXPENSIVE' -%} var(--wa-bg-warning)
            {%- else -%} var(--wa-bg-danger)
            {%- endif -%} !important;
          --chip-border-width: 0px !important;
          --chip-font-size: 12px !important;
          color: var(--primary-text-color) !important;
        }
  - type: template
    entity: light.lampor_inomhus
    icon: mdi:lightbulb-on-outline
    content: >-
      {{ expand('light.lampor_inomhus') | selectattr('state','eq','on') | list |
      count + expand('light.lampor_utomhus') | selectattr('state','eq','on') |
      list | count }}
    tap_action:
      action: navigate
      navigation_path: rum
    hold_action:
      action: none
    double_tap_action:
      action: none
    card_mod:
      style: |
        ha-card {
          --chip-background: {% set total_lights = expand('light.lampor_inomhus') | selectattr('state','eq','on') | list | count + expand('light.lampor_utomhus') | selectattr('state','eq','on') | list | count %}
            {%- if total_lights == 0 -%} var(--wa-bg-success)
            {%- else -%} var(--wa-bg-warning)
            {%- endif -%} !important;
          --chip-border-width: 0px !important;
          --chip-font-size: 12px !important;
          color: var(--primary-text-color) !important;
        }
  - type: template
    entity: switch.alla_kameror
    icon: mdi:camera
    content: >-
      {{ expand('switch.alla_kameror') | selectattr('state','eq','off') | list |
      count }}
    tap_action:
      action: navigate
      navigation_path: /lovelace/kameror
    hold_action:
      action: more-info
    double_tap_action:
      action: more-info
    card_mod:
      style: |
        ha-card {
          --chip-background: {% set active_cameras = expand('switch.alla_kameror') | selectattr('state','eq','on') | list | count %}
            {%- if active_cameras == 0 -%} var(--wa-bg-success)
            {%- else -%} var(--wa-bg-danger)
            {%- endif -%} !important;
          --chip-border-width: 0px !important;
          --chip-font-size: 12px !important;
          color: var(--primary-text-color) !important;
        }
  - type: template
    entity: binary_sensor.alla_sensorer
    icon: mdi:door-open
    content: >-
      {{ expand('binary_sensor.alla_sensorer') | selectattr('state','eq','on') |
      list | count }}
    tap_action:
      action: navigate
      navigation_path: /lovelace/rum
    hold_action:
      action: none
    double_tap_action:
      action: none
    card_mod:
      style: |
        ha-card {
          --chip-background: {% set open_sensors = expand('binary_sensor.alla_sensorer') | selectattr('state','eq','on') | list | count %}
            {%- if open_sensors == 0 -%} var(--wa-bg-success)
            {%- else -%} var(--wa-bg-danger)
            {%- endif -%} !important;
          --chip-border-width: 0px !important;
          --chip-font-size: 12px !important;
          color: var(--primary-text-color) !important;
        }
  - type: entity
    entity: alarm_control_panel.alarmo
    content_info: state
    tap_action:
      action: navigate
      navigation_path: /lovelace/larm
    card_mod:
      style: |
        ha-card {
          --chip-background: {% set alarm_state = states('alarm_control_panel.alarmo') %}
            {%- if alarm_state == 'disarmed' -%} var(--wa-bg-success)
            {%- elif alarm_state == 'armed_home' -%} var(--wa-bg-warning)
            {%- elif alarm_state == 'armed_away' -%} var(--wa-bg-info)
            {%- elif alarm_state == 'armed_night' -%} var(--wa-bg-purple)
            {%- elif alarm_state == 'triggered' -%} var(--wa-bg-danger)
            {%- elif alarm_state == 'pending' -%} var(--wa-bg-warning)
            {%- else -%} var(--wa-bg-neutral)
            {%- endif -%} !important;
          --chip-border-width: 0px !important;
          --chip-font-size: 12px !important;
          color: var(--primary-text-color) !important;
        }
  - type: template
    entity: switch.garageport
    icon: mdi:garage
    content: "{{ state_translated(\"binary_sensor.garageport_sensor_contact\") }} "
    tap_action:
      action: more-info
    hold_action:
      action: more-info
    double_tap_action:
      action: more-info
    card_mod:
      style: |
        ha-card {
          --chip-background: {% set port_state = states('binary_sensor.garageport_sensor_contact') %}
            {%- if port_state == 'off' -%} var(--wa-bg-success)
            {%- elif port_state == 'on' -%} var(--wa-bg-danger)
            {%- else -%} var(--wa-bg-neutral)
            {%- endif -%} !important;
          --chip-border-width: 0px !important;
          --chip-font-size: 12px !important;
          color: var(--primary-text-color) !important;
        }
  - type: template
    entity: calendar.kalendar
    icon: mdi:calendar
    content: |-
      {% set event_title = state_attr('calendar.kalendar', 'message') %}
      {% set event_start = state_attr('calendar.kalendar', 'start_time') %}
      {% set all_day = state_attr('calendar.kalendar', 'all_day') %}

      {% if event_title %}
        {% if all_day %}
          {% set start_date = as_timestamp(event_start) | timestamp_custom('%d/%m') %}
          {% set today = now().strftime('%d/%m') %}
          {% set tomorrow = (now() + timedelta(days=1)).strftime('%d/%m') %}
          {% if start_date == today %}
            {{ event_title }} (idag)
          {% elif start_date == tomorrow %}
           {{ event_title }} (imorgon)
          {% else %}
            {{ event_title }} ({{ start_date }})
          {% endif %}
        {% else %}
          {% set start_time = as_timestamp(event_start) | timestamp_custom('%H:%M') %}
          {% set start_date = as_timestamp(event_start) | timestamp_custom('%d/%m') %}
          {% set today = now().strftime('%d/%m') %}
          {% set tomorrow = (now() + timedelta(days=1)).strftime('%d/%m') %}
          {% if start_date == today %}
            {{ event_title }} ({{ start_time }})
          {% elif start_date == tomorrow %}
            {{ event_title }} (imorgon {{ start_time }})
          {% else %}
            {{ event_title }} ({{ start_date }} {{ start_time }})
          {% endif %}
        {% endif %}
      {% else %}
        Inga events
      {% endif %}
    tap_action:
      action: navigate
      navigation_path: /calendar
    hold_action:
      action: more-info
    double_tap_action:
      action: more-info
    card_mod:
      style: |
        ha-card {
          --chip-background: {% set event_title = state_attr('calendar.kalendar', 'message') %}
            {% if event_title %}
              {% if is_state('calendar.kalendar', 'on') %} var(--wa-bg-danger)
              {% else %} var(--wa-bg-warning)
              {% endif %}
            {% else %}
              var(--wa-bg-success)
            {% endif %} !important;
          --chip-border-width: 0px !important;
          --chip-font-size: 12px !important;
          color: var(--primary-text-color) !important;
        }
  - type: conditional
    conditions:
      - condition: state
        entity: input_boolean.sommartid_switch
        state: "on"
    chip:
      type: template
      entity: lawn_mower.mova_600
      icon: mdi:robot-mower
      content: >-
        {% set charging_status = states('sensor.mova_600_charging_status') %} {%
        set state = states('lawn_mower.mova_600') %} {% set battery =
        states('sensor.mova_600_batteri') %} {% if charging_status == 'charging'
        %}
          Laddar {{ battery }}%
        {% elif state == 'mowing' %}
          Klipper {{ battery }}%
        {% elif state == 'docked' %}
          Dockad {{ battery }}%
        {% elif state == 'returning' %}
          Återvänder {{ battery }}%
        {% elif state == 'paused' %}
          Pausad {{ battery }}%
        {% elif state == 'error' %}
          Fel {{ battery }}%
        {% else %}
          {{ state | title }} {{ battery }}%
        {% endif %}
      tap_action:
        action: more-info
      hold_action:
        action: more-info
      double_tap_action:
        action: more-info
      card_mod:
        style: |
          ha-card {
            --chip-background: {% set mower_state = states('lawn_mower.mova_600') %} {% set charging_status = states('sensor.mova_600_charging_status') %}
              {%- if mower_state == 'mowing' -%} var(--wa-bg-success)
              {%- elif mower_state == 'docked' and charging_status == 'charging' -%} var(--wa-bg-warning)
              {%- elif mower_state == 'docked' -%} var(--wa-bg-info)
              {%- elif mower_state == 'returning' -%} var(--wa-bg-warning)
              {%- elif mower_state == 'paused' -%} var(--wa-bg-warning)
              {%- elif mower_state == 'error' -%} var(--wa-bg-danger)
              {%- else -%} var(--wa-bg-neutral)
              {%- endif -%} !important;
            --chip-border-width: 0px !important;
            --chip-font-size: 12px !important;
            color: var(--primary-text-color) !important;
          }
  - type: template
    entity: vacuum.q8_max
    icon: mdi:robot-vacuum
    content: >-
      {% set state = states('vacuum.q8_max') %} {% set battery =
      states('sensor.q8_max_batteri_2') %} {% set progress =
      states('sensor.q8_max_cleaning_progress') %} {% if state == 'cleaning' %}
        Städar {{ progress }}%
      {% elif state == 'docked' and battery | int < 100 %}
        Laddar {{ battery }}%
      {% elif state == 'docked' %}
        Dockad {{ battery }}%
      {% elif state == 'returning' %}
        Återvänder {{ battery }}%
      {% elif state == 'paused' %}
        Pausad {{ battery }}%
      {% elif state == 'error' %}
        Fel {{ battery }}%
      {% else %}
        {{ state | title }} {{ battery }}%
      {% endif %}
    tap_action:
      action: navigate
      navigation_path: "#dammsugare"
    hold_action:
      action: more-info
    double_tap_action:
      action: more-info
    card_mod:
      style: |
        ha-card {
          --chip-background: {% set vacuum_state = states('vacuum.q8_max') %}
            {%- if vacuum_state == 'cleaning' -%} var(--wa-bg-info)
            {%- elif vacuum_state == 'docked' and states('sensor.q8_max_batteri_2') | int < 100 -%} var(--wa-bg-warning)
            {%- elif vacuum_state == 'docked' -%} var(--wa-bg-info)
            {%- elif vacuum_state == 'returning' -%} var(--wa-bg-purple)
            {%- elif vacuum_state == 'paused' -%} var(--wa-bg-warning)
            {%- elif vacuum_state == 'error' -%} var(--wa-bg-danger)
            {%- else -%} var(--wa-bg-neutral)
            {%- endif -%} !important;
          --chip-border-width: 0px !important;
          --chip-font-size: 12px !important;
          color: var(--primary-text-color) !important;
        }
  - type: template
    entity: sensor.robotdammsugare_robot_cleaner_movement
    icon: mdi:robot-vacuum-variant
    content: >-
      {% set state = states('sensor.robotdammsugare_robot_cleaner_movement') %}
      {% set battery = states('sensor.robotdammsugare_battery') | int(0) %}  {%
      if state == 'cleaning' %}
        Städar {{ battery }}%
      {% elif state == 'charging' and battery < 100 %}
        Laddar {{ battery }}%
      {% elif state == 'idle' %}
        Vilande {{ battery }}%
      {% elif state == 'homing' %}
        Återvänder {{ battery }}%
      {% elif state == 'pause' %}
        Pausad {{ battery }}%
      {% elif state == 'alarm' %}
        Fel {{ battery }}%
      {% elif state == 'off' %}
        Avstängd {{ battery }}%
      {% elif state == 'reserve' %}
        Reserv {{ battery }}%
      {% elif state == 'point' %}
        Punktstädning {{ battery }}%
      {% elif state == 'after' %}
        Efterstädning {{ battery }}%
      {% elif battery == 100 %}
        Dockad {{ battery }}%
      {% else %}
        {{ state | title }} {{ battery }}%
      {% endif %}
    tap_action:
      action: navigate
      navigation_path: "#dammsugare"
    hold_action:
      action: more-info
    double_tap_action:
      action: more-info
    card_mod:
      style: |
        ha-card {
          --chip-background: {% set vacuum_state = states('sensor.robotdammsugare_robot_cleaner_movement') %}
            {% set battery = states('sensor.robotdammsugare_battery') | int(0) %}
            {%- if vacuum_state == 'cleaning' -%} var(--wa-bg-info)
            {%- elif vacuum_state == 'charging' and battery < 100 -%} var(--wa-bg-warning)
            {%- elif battery == 100 -%} var(--wa-bg-info)
            {%- elif vacuum_state == 'idle' -%} var(--wa-bg-info)
            {%- elif vacuum_state == 'homing' -%} var(--wa-bg-purple)
            {%- elif vacuum_state == 'pause' -%} var(--wa-bg-warning)
            {%- elif vacuum_state == 'alarm' -%} var(--wa-bg-danger)
            {%- elif vacuum_state == 'after' -%} var(--wa-bg-success)
            {%- else -%} var(--wa-bg-neutral)
            {%- endif -%} !important;
          --chip-border-width: 0px !important;
          --chip-font-size: 12px !important;
          color: var(--primary-text-color) !important;
        }
  - type: template
    entity: switch.kaffebryggare_switch
    icon: mdi:coffee-maker
    content: |-
      {% if is_state('switch.kaffebryggare_switch', 'on') %}
        {% if is_state('timer.kaffebryggare', 'active') %}
          {% set duration = state_attr('timer.kaffebryggare', 'duration') %}
          {% set finishes_at = state_attr('timer.kaffebryggare', 'finishes_at') %}
          {% if finishes_at %}
            {% set remaining_seconds = (as_timestamp(finishes_at) - as_timestamp(now())) | int %}
            {% if remaining_seconds > 0 %}
              {% set hours = (remaining_seconds // 3600) %}
              {% set minutes = ((remaining_seconds % 3600) // 60) %}
              {% set seconds = (remaining_seconds % 60) %}
              {% if hours > 0 %}
                På ({{ '%d:%02d:%02d' | format(hours, minutes, seconds) }})
              {% else %}
                På ({{ '%02d:%02d' | format(minutes, seconds) }})
              {% endif %}
            {% else %}
              På (avslutas...)
            {% endif %}
          {% else %}
            På ({{ duration }})
          {% endif %}
        {% else %}
          På
        {% endif %}
      {% else %}
        Av
      {% endif %}
    tap_action:
      action: more-info
    hold_action:
      action: more-info
    double_tap_action:
      action: more-info
    card_mod:
      style: |
        ha-card {
          --chip-background: var(--wa-bg-brown) !important;
          --chip-border-width: 0px !important;
          --chip-font-size: 12px !important;
          color: var(--primary-text-color) !important;
        }
  - type: template
    entity: sensor.pooltemp_senaste_giltiga
    icon: mdi:pool
    icon_color: var(--wa-info)
    content: >-
      {% set days = ((now().timestamp() -
      states('input_datetime.lagga_klor_i_poolen') | as_timestamp(0)) / 86400) |
      round(0, default=0) %} {{ states('sensor.pooltemp_senaste_giltiga') |
      float(0) | round(1) }} °C ({{ days }}d)
    tap_action:
      action: more-info
    hold_action:
      action: call-service
      service: script.1715506639747
    double_tap_action:
      action: more-info
      entity: sensor.ibs_th2_p01b_04d6_temperature
    card_mod:
      style: |
        ha-card {
          --chip-background: {% if states('sensor.ibs_th2_p01b_04d6_temperature') == 'unavailable' %} var(--wa-bg-danger)
          {% else %} var(--wa-bg-info)
          {% endif %} !important;
          --chip-border-width: 0px !important;
          --chip-font-size: 12px !important;
          color: var(--primary-text-color) !important;
        }
  - type: template
    icon: mdi:update
    icon_color: |-
      {% set updates = states.update 
        | selectattr('state', 'eq', 'on') 
        | list | count %}
      {% if updates > 0 %}
        var(--wa-warning)
      {% else %}
        var(--wa-success)
      {% endif %}
    content: |-
      {% set updates = states.update 
        | selectattr('state', 'eq', 'on') 
        | list | count %}
      {{ updates }}
    tap_action:
      action: navigate
      navigation_path: /config/dashboard
    hold_action:
      action: more-info
  - type: template
    icon: mdi:bell
    icon_color: >-
      {% set notifications = states | selectattr('domain', 'eq',
      'persistent_notification') | list | count %} {% if notifications > 0 %}
        var(--wa-warning)
      {% else %}
        var(--wa-success)
      {% endif %}
    content: >-
      {% set notifications = states | selectattr('domain', 'eq',
      'persistent_notification') | list | count %} {{ notifications }}
    tap_action:
      action: navigate
      navigation_path: /config/logs
    hold_action:
      action: more-info
card_mod:
  style:
    mushroom-template-chip:nth-child(10)$: |
      ha-state-icon {
        animation: door 3s steps(1) infinite alternate; 
      }
      @keyframes door {
        0% { clip-path: inset(0 0 0 0); }
        25%  { clip-path: polygon(0 0, 100% 0, 100% 100%, 68% 100%, 69% 73%, 32% 73%, 31% 100%, 0 100%); }
        50%  { clip-path: polygon(0 0, 100% 0, 100% 100%, 68% 100%, 69% 61%, 32% 61%, 31% 100%, 0 100%); }
        75% { clip-path: polygon(0 0, 100% 0, 100% 100%, 68% 100%, 69% 48%, 32% 48%, 31% 100%, 0 100%); }
      }
    mushroom-template-chip:nth-child(13)$: |
      ha-state-icon {
        {% if is_state('vacuum.q8_max', 'cleaning') %}
          animation: wobbling 0.7s linear infinite alternate;
          color: var(--wa-info) !important;
        {% endif %}
      }
      @keyframes wobbling {
        0% { transform: rotate(-25deg); }
        100% { transform: rotate(25deg); }
      }
    mushroom-template-chip:nth-child(14)$: |
      ha-state-icon {
        {% if is_state('sensor.robotdammsugare_robot_cleaner_movement', 'cleaning') %}
          animation: wobbling 0.7s linear infinite alternate;
          color: var(--wa-info) !important;
        {% endif %}
      }
      @keyframes wobbling {
        0% { transform: rotate(-25deg); }
        100% { transform: rotate(25deg); }
      }
    mushroom-template-chip:nth-child(15)$: |
      ha-state-icon {
        {% if is_state('switch.kaffebryggare_switch', 'on') %}
          animation: steam 2s ease-in-out infinite alternate;
          color: var(--wa-warning) !important;
        {% else %}
          color: var(--wa-neutral) !important;
        {% endif %}
      }
      @keyframes steam {
        0% { transform: translateY(0px) scale(1); opacity: 1; }
        50% { transform: translateY(-1px) scale(1.05); opacity: 0.9; }
        100% { transform: translateY(-2px) scale(1.1); opacity: 0.8; }
      }
