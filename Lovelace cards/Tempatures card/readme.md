# Tempatures card

I am using Python to format code blocks because it's the closest thing to HA color formatting. This is just for me to undestand the templates much more faster 

This solution requires Mushroom cards.  
I am using Horizontal stack and for each row I'm using vertical stack. Within vertical stack I have Mushroom template cards for each sensor.

# Living room
```python
{% if states('sensor.ble_temperature_ruuvitag_living_room') | float < 20 %} 
blue
{% elif states('sensor.ble_temperature_ruuvitag_living_room') | float > 20 and states('sensor.ble_temperature_ruuvitag_living_room') | float < 23 %}
green
{% elif states('sensor.ble_temperature_ruuvitag_living_room') | float > 23 and states('sensor.ble_temperature_ruuvitag_living_room') | float < 27 %}
orange
{% elif states('sensor.ble_temperature_ruuvitag_living_room') | float > 27 %}
red
{% endif %}
```
## Primary information
```python
{{ states('sensor.ble_temperature_ruuvitag_living_room') |float | round(2) }} °C
```
# Bedroom
## Icon color
```python
{% if states('sensor.ble_temperature_ruuvitag_bedroom') | float < 20 %} 
blue
{% elif states('sensor.ble_temperature_ruuvitag_bedroom') | float > 20 and states('sensor.ble_temperature_ruuvitag_bedroom') | float < 23 %}
green
{% elif states('sensor.ble_temperature_ruuvitag_bedroom') | float > 23 and states('sensor.ble_temperature_ruuvitag_bedroom') | float < 27 %}
orange
{% elif states('sensor.ble_temperature_ruuvitag_bedroom') | float > 27 %}
red
{% endif %}
```

## Primary information
```Python
{{ states('sensor.ble_temperature_ruuvitag_bedroom') | float | round(2) }} °C
```
# Kitchen
## Icon color
```python
{% if states('sensor.ble_temperature_ruuvitag_kitchen') | float < 20 %} 
blue
{% elif states('sensor.ble_temperature_ruuvitag_kitchen') | float > 20 and states('sensor.ble_temperature_ruuvitag_kitchen') | float < 23 %}
green
{% elif states('sensor.ble_temperature_ruuvitag_kitchen') | float > 23 and states('sensor.ble_temperature_ruuvitag_kitchen') | float < 27 %}
orange
{% elif states('sensor.ble_temperature_ruuvitag_kitchen') | float > 27 %}
red
{% endif %}
```

## Primary information
```python
{{ states('sensor.ble_temperature_ruuvitag_kitchen') | float | round(2) }} °C
```
# Sauna
## Icon
```python
{% if states('sensor.ble_temperature_ruuvitag_sauna') | float < 35 %} 
mdi:thermometer
{% elif states('sensor.ble_temperature_ruuvitag_sauna') | float > 35 and states('sensor.ble_temperature_ruuvitag_sauna') | float < 50 %}
mdi:heat-wave
{% elif states('sensor.ble_temperature_ruuvitag_sauna') | float > 50 and states('sensor.ble_temperature_ruuvitag_sauna') | float < 55 %}
mdi:thermometer-low
{% elif states('sensor.ble_temperature_ruuvitag_sauna') | float > 55 and states('sensor.ble_temperature_ruuvitag_sauna') | float < 59 %}
mdi:thermometer-plus
{% elif states('sensor.ble_temperature_ruuvitag_sauna') | float > 59 and states('sensor.ble_temperature_ruuvitag_sauna') | float < 65 %}
mdi:thermometer
{% elif states('sensor.ble_temperature_ruuvitag_sauna') | float > 55 and states('sensor.ble_temperature_ruuvitag_sauna') | float < 69 %}
mdi:thermometer-high
{% elif states('sensor.ble_temperature_ruuvitag_sauna') | float > 69 %}
mdi:coffin
{% endif %}
```
## Icon color
```python
{% if states('sensor.ble_temperature_ruuvitag_sauna') | float < 50 %} 
blue
{% elif states('sensor.ble_temperature_ruuvitag_sauna') | float > 50 and states('sensor.ble_temperature_ruuvitag_sauna') | float < 55 %}
cyan
{% elif states('sensor.ble_temperature_ruuvitag_sauna') | float > 55 and states('sensor.ble_temperature_ruuvitag_sauna') | float < 59 %}
lime
{% elif states('sensor.ble_temperature_ruuvitag_sauna') | float > 59 and states('sensor.ble_temperature_ruuvitag_sauna') | float < 65 %}
green
{% elif states('sensor.ble_temperature_ruuvitag_sauna') | float > 55 and states('sensor.ble_temperature_ruuvitag_sauna') | float < 69 %}
orange
{% elif states('sensor.ble_temperature_ruuvitag_sauna') | float > 69 %}
red
{% endif %}
```

## Primary information
```python
{{ states('sensor.ble_temperature_ruuvitag_sauna') | float | round(2) }} °C
```
# Nerd cave
## Icon color
```python
{% if states('sensor.ble_temperature_ruuvitag_the_room') | float < 20 %} 
blue
{% elif states('sensor.ble_temperature_ruuvitag_the_room') | float > 20 and states('sensor.ble_temperature_ruuvitag_the_room') | float < 23 %}
green
{% elif states('sensor.ble_temperature_ruuvitag_the_room') | float > 23 and states('sensor.ble_temperature_ruuvitag_the_room') | float < 27 %}
orange
{% elif states('sensor.ble_temperature_ruuvitag_the_room') | float > 27 %}
red
{% endif %}
```

## Primary information
```python
{{ states('sensor.ble_temperature_ruuvitag_the_room') | float | round(2) }} °C
```
# Outside weather

## Primary information
```python
{{ states('sensor.kaikala_temperature') }} °C
```

## Icon
```python
{% if states('sensor.kaikala_temperature') | float <= -20 %}
mdi:skull
{% elif states('sensor.kaikala_temperature') | float > -20 and states('sensor.kaikala_temperature') | float < 0 %}
mdi:snowflake-thermometer
{% elif states('sensor.kaikala_temperature') | float > 0 and states('sensor.kaikala_temperature') | float < 15 %}
mdi:thermometer
{% elif states('sensor.kaikala_temperature') | float > 15  and states('sensor.kaikala_temperature') | float < 27 %}
mdi:sun-thermometer
{% elif states('sensor.kaikala_temperature') | float >= 27 %}
mdi:fire
{% endif %}
```

## Icon Color
```python
{% if states('sensor.kaikala_temperature') | float < -15 %} 
white
{% elif states('sensor.kaikala_temperature') | float > -15 and states('sensor.kaikala_temperature') | float < 0 %}
#33F2FF
{% elif states('sensor.kaikala_temperature') | float > 0 and states('sensor.kaikala_temperature') | float < 5 %}
#2CF2BD
{% elif states('sensor.kaikala_temperature') | float > 5 and states('sensor.kaikala_temperature') | float < 15 %}
#C5F3DB
{% elif states('sensor.kaikala_temperature') | float > 15 and states('sensor.kaikala_temperature') | float < 20 %}
#2BF389
{% elif states('sensor.kaikala_temperature') | float > 20 and states('sensor.kaikala_temperature') | float < 23 %}
green
{% elif states('sensor.kaikala_temperature') | float > 23 and states('sensor.kaikala_temperature') | float < 27 %}
orange
{% elif states('sensor.kaikala_temperature') | float > 27 %}
red
{% endif %}
```