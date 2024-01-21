# Nordpool cheapest price countdown

Jinja template for informing when is the next time for cheapest electricity

1. Requires nordpool integration
2. Modify following variables to match your nordpool entity
  - prices_today
  - prices_today_min_value
  - prices_tomorrow

```javascript
{## Configurations ##}
{% set global = namespace(today_counter = 0, tomorrow_counter = 0, today_cheapest_time = None, tomorrow_cheapest_time = None) %}
{% set prices_today = state_attr('sensor.nordpool_kwh_fi_eur_4_095_024', 'raw_today') %}
{% set prices_today_min_value = state_attr('sensor.nordpool_kwh_fi_eur_4_095_024', 'min') %}
{% set prices_tomorrow = state_attr('sensor.nordpool_kwh_fi_eur_4_095_024', 'raw_tomorrow') %}
{% set prices_tomorrow_min_value = prices_tomorrow | map(attribute='value') | list | min %}

{## Logic for today and tomorrow prices ##}
{% for item in prices_today %}
  {% set global.today_counter = global.today_counter + 1 %}
  {% if item['value'] == prices_today_min_value %}
    {% set global.today_cheapest_time = item['start'] %}
  {% endif %}
{% endfor %}

{% for item in prices_tomorrow %}
  {% set global.tomorrow_counter = global.tomorrow_counter + 1 %}
  {% if item['value'] == prices_tomorrow_min_value %}
    {% set global.tomorrow_cheapest_time = item['start'] %}
  {% endif %}
{% endfor %}

{## Print logic ##}
{% if global.today_cheapest_time %}
  {% set cheapest_timestamp = as_timestamp(global.today_cheapest_time) %}
  {% set current_timestamp = as_timestamp(now()) %}
  {% set time_difference = cheapest_timestamp - current_timestamp %}
  {% set hours_left = time_difference // 3600 %}
  {% set minutes_left = (time_difference % 3600) // 60 %}
  
  {# Check if hours starts with - then get cheapest time for tomorrow #}
  {% if hours_left|string|regex_match('^\\-.*') %}
    {% set cheapest_timestamp = as_timestamp(global.tomorrow_cheapest_time) %}
    {% set current_timestamp = as_timestamp(now()) %}
    {% set time_difference = cheapest_timestamp - current_timestamp %}
  
    {% set hours_left = time_difference // 3600 %}
    {% set minutes_left = (time_difference % 3600) // 60 %}
    Time left to cheapest price: {{ hours_left }} hours and {{ minutes_left }} minutes
  {% else %}
    Time left to cheapest price: {{ hours_left }} hours and {{ minutes_left }} minutes
  {% endif %}
{% endif %}
```