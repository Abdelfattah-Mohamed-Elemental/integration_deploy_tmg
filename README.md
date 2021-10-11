# integration_deploy_tmg
type: entity-filter
entities:
  - light.bed_light
  - light.ceiling_lights
  - light.kitchen_lights
state_filter:
  - 'on'
card:
  type: markdown
  content: |
    The lights that are on are:
    {% for l in config.entities %}
      - {{ l.entity }}
    {%- endfor %}

    And the door is {% if is_state('binary_sensor.door', 'on') %} open {% else %} closed {% endif %}.
