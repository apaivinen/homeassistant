

# awake or sleep.json
Trigger tag (or manual inject) to set input_select helper value based on time and current value.

```sequence
If current helper value is Sleep then check if time is between 3:30 - 18:00
If true --> set helper value to Awake
If False --> do nothing

If current helper value is Awake then check if time is between 18:00 - 3:30
If true --> set helper value to Sleep
If False --> do nothing
```
input_select helper values are triggering home assistant automations

# Flower.json
Just simple check if humidity is less than 40% then send a notification. Trigger is time based every day at 12:00

# is anybody home.json
Checks from unifi controller if phone mac address is found from WIFI.  
Remember to add mac address to Phone1 checks node

>**Important!**  
>This flow requires node-red-contrib-unifi palette to be installed

There's also tag triggered person state change under construction.