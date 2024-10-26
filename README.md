# i3-battery-notification
Battery monitoring script for i3wm.

This script was inspired by rjekker/i3-battery-popup, but using python instead of pure shell script.
It monitors your battery levels and send notifications when it is low, or full charge.

## Pics
- Notify-send low battery default popup
![image](https://github.com/user-attachments/assets/4ef49bca-59ac-4bf6-a2d8-a5cc5b07d87b)
- Notify-send full battery default popup
![image](https://github.com/user-attachments/assets/b38d544d-8f68-43d2-bd0f-94b3f8558207)
- Nagbar full battery default popup
![image](https://github.com/user-attachments/assets/271af624-b8e2-4cf9-aabf-71e3ae443d80)
- Nagbar low battery default popup
![image](https://github.com/user-attachments/assets/ed4502c2-615b-482d-bb08-0a92a288b027)

## Instructions to use
1. Download i3-battery-notification
2. Include it in your PATH (If you don't know how PATH works, you can just store it in /bin/)
3. Open i3 config file (probably ~/.config/i3/config)
4. Include `exec --no-startup-id i3-battery-notification` (if it doesn't work, use the absolute path, exemple: `exec --no-startup-id /bin/i3-battery-popup`)
5. Log in again, and it will be running
## Options
- `-l`: Low Percentage: Below this value, it will notify low battery. Default 20.
- `-m`: Full Percentage: Above this value, it will notify full charge. Default 95.
- `-i`: Interval: Time between each notification, in minutes. Default 5.
- `-d`: Debug mode
- `-c`: Sets the file containing battery capacity level. Default is /sys/class/power_supply/BAT0/capacity
- `-s`: Sets the file containing battery status (Charging, Discharging, etc.). Default is /sys/class/power_supply/BAT0/status
- `-n`: Enables notify-send instead of i3-nagbar popup
### Example
`i3-battery-popup -l 15 -m 95 -i 5 -n` -> Sets notification to be sent with notify-send (compatible with dunst), will popup when battery is discharging and less than 15%, or when battery is charging and more than 95%, and will repeat every 5 minutes.
