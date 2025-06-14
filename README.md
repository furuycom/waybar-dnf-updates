# waybar-dnf-updates
![waybar-dnf-updates](https://github.com/user-attachments/assets/42ceaad1-af96-41b4-9f2d-b7c00321afde)

Download the `checkupdates.sh` script, put it in `$HOME/.config/waybar/scripts/checkupdates.sh`.

To configure, add the following to your Waybar config (`$HOME/.config/waybar/config`).


```json
    "custom/updates": {
    "exec": "bash $HOME/.config/waybar/scripts/checkupdates.sh", // <--- path to script
    "on-click-right": "bash $HOME/.config/waybar/scripts/checkupdates.sh", // refresh on right click
    "on-click-middle": "swaymsg exec '$term -e sudo dnf update --refresh'", // update on middle click    
    "interval": 900, // refresh every 15 minutes
    "return-type": "json",
    "format": "{icon}",
    "format-alt": "{icon} {}",
    "format-icons": {
        "has-updates": "", // icon when updates needed
        "updated": "" // icon when all packages updated
    }
    },
```

To style use the `#custom-updates` ID in your Waybar styles file (`~/.config/waybar/styles.css`).

For more information see the [Waybar wiki](https://github.com/Alexays/Waybar/wiki).



