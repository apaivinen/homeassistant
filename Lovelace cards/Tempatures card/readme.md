I am using Python to format code blocks because it's the closest thing to HA color formatting. This is just for me to undestand the templates much more faster

This solution requires Mushroom cards.  
I am using Horizontal stack and for each row I'm using vertical stack. Within vertical stack I have Mushroom template cards for each sensor.
# Living room
Entity: RuuviTag 38A7 Olohuone Temperature

```python
{% if states(entity) | float <= 20 %} 
blue
{% elif states(entity) | float > 20 and states(entity) | float < 23 %}
green
{% elif states(entity) | float >= 23 and states(entity) | float < 27 %}
orange
{% elif states(entity) | float >= 27 %}
red
{% endif %}
```
## Primary information
```python
{{ states(entity) |float | round(2) }} °C
```
# Bedroom
Entity: RuuviTag C5F2 Makuuhuone Temperature
## Icon color
```python
{% if states(entity) | float <= 20 %} 
blue
{% elif states(entity) | float > 20 and states(entity) | float < 23 %}
green
{% elif states(entity) | float >= 23 and states(entity) | float < 27 %}
orange
{% elif states(entity) | float >= 27 %}
red
{% endif %}
```

## Primary information
```Python
{{ states(entity) |float | round(2) }} °C
```
# Kitchen
Entity: RuuviTag 8C31 Keittiö Temperature
## Icon color
```python
{% if states(entity) | float <= 20 %} 
blue
{% elif states(entity) | float > 20 and states(entity) | float < 23 %}
green
{% elif states(entity) | float >= 23 and states(entity) | float < 27 %}
orange
{% elif states(entity) | float >= 27 %}
red
{% endif %}
```

## Primary information
```python
{{ states(entity) | float | round(2) }} °C
```
# Sauna
Entity: RuuviTag FC91 Sauna Temperature
## Icon
```python
{% if states(entity) | float <= 35 %} 
mdi:thermometer
{% elif states(entity) | float > 35 and states(entity) | float < 50 %}
mdi:heat-wave
{% elif states(entity) | float >= 50 and states(entity) | float < 55 %}
mdi:thermometer-low
{% elif states(entity) | float >= 55 and states(entity) | float < 59 %}
mdi:thermometer-plus
{% elif states(entity) | float >= 59 and states(entity) | float < 65 %}
mdi:thermometer
{% elif states(entity) | float >= 55 and states(entity) | float < 69 %}
mdi:thermometer-high
{% elif states(entity) | float >= 69 %}
mdi:coffin
{% endif %}
```
## Icon color
```python
{% if states(entity) | float <= 50 %} 
blue
{% elif states(entity) | float > 50 and states(entity) | float < 55 %}
cyan
{% elif states(entity) | float >= 55 and states(entity) | float < 59 %}
lime
{% elif states(entity) | float >= 59 and states(entity) | float < 65 %}
green
{% elif states(entity) | float >= 55 and states(entity) | float < 69 %}
orange
{% elif states(entity) | float >= 69 %}
red
{% endif %}
```

## Primary information
```python
{{ states('sensor.ble_temperature_ruuvitag_sauna') | float | round(2) }} °C
```
# Nerd cave
Entity: RuuviTag 76A0 Työhuone Temperature
## Icon color
```python
{% if states(entity) | float <= 20 %} 
blue
{% elif states(entity) | float > 20 and states(entity) | float < 23 %}
green
{% elif states(entity) | float >= 23 and states(entity) | float < 27 %}
orange
{% elif states(entity) | float >= 27 %}
red
{% endif %}
```

## Primary information
```python
{{ states(entity) | float | round(2) }} °C
```
# Outside weather

## Primary information

Entity: Käikälä Temperature

```python
{{ states(entity) }} °C
```

## Icon
```python
{% if states(entity) | float <= -20 %}
mdi:skull
{% elif states(entity) | float > -20 and states(entity) | float < 0 %}
mdi:snowflake-thermometer
{% elif states(entity) | float >= 0 and states(entity) | float < 15 %}
mdi:thermometer
{% elif states(entity) | float >= 15  and states(entity) | float < 27 %}
mdi:sun-thermometer
{% elif states(entity) | float >= 27 %}
mdi:skull-crossbones
{% endif %}
```

## Icon Color
```python
{% if states(entity) | float < -15 %} 
white
{% elif states(entity) | float > -15 and states(entity) | float < 0 %}
#33F2FF
{% elif states(entity) | float > 0 and states(entity) | float < 5 %}
#2CF2BD
{% elif states(entity) | float > 5 and states(entity) | float < 15 %}
#C5F3DB
{% elif states(entity) | float > 15 and states(entity) | float < 20 %}
#2BF389
{% elif states(entity) | float > 20 and states(entity) | float < 23 %}
green
{% elif states(entity) | float > 23 and states(entity) | float < 27 %}
orange
{% elif states(entity) | float > 27 %}
red
{% endif %}
```