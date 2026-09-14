

### Why It Worked

1. **Stopped System-Wide PulseAudio:** Running `./rc.pulseaudio stop` killed the system-wide daemon, which was running as `root`. System-wide mode drops security privileges and disables dynamic module loading, preventing BlueZ from registering audio endpoints.
    
2. **Killed/Restarted User-Level PulseAudio:** Running `pulseaudio -k && pulseaudio --start` under `eduardo` launched a clean user-space PulseAudio session. This allowed standard D-Bus IPC to communicate with `bluetoothd`.
    
3. **Module Auto-Discovery:** When `pactl load-module module-bluetooth-policy` returned `Module initialization failed`, it confirmed that PulseAudio's `module-bluetooth-policy` and `module-bluez5-discover` were **already automatically loaded** by default in your user session.
    
4. **Endpoint Registration:** Because user-space PulseAudio was running with active Bluetooth modules, it successfully registered its media endpoints (A2DP) with BlueZ. When you ran `bluetoothctl`, BlueZ negotiated the audio transport stream (`sep1/fd0 State: active`), and your JBL headphones connected on the standard profile.
    

### Step-by-Step Procedure to Reproduce / Connect

Use this streamlined flow whenever you need to reconnect or if Bluetooth audio drops.

#### **Step 1: Ensure User-Space PulseAudio Is Running**

Run these commands in a regular user terminal (`eduardo@eoc`, **do not use `root`**):

``` bash 
# Restart the user-space audio server 
pulseaudio -k && pulseaudio --start
```

#### **Step 2: Connect the Headphones**

Open `bluetoothctl` and trigger the connection for the **standard audio profile** (`2C:FD:B3:29:8C:80`):

``` bash 
bluetoothctl
```

Inside the `bluetoothctl` prompt, run:

``` plaintext
power on 
connect 2C:FD:B3:29:8C:80
```

_Look for `State: active` or `Connection successful` in the terminal output._

#### **Step 3: Select Audio Output in XFCE**

1. Open **Volume Control** (`pavucontrol` in XFCE).
    
2. Go to the **Configuration** tab.
    
3. Ensure **JBL LIVE660NC** is set to **A2DP Sink** (High Fidelity Playback).
    
4. Go to the **Output Devices** tab and select **JBL LIVE660NC** as your default output device.
    

### Preventing the Issue on Reboot (Slackware Config)

To ensure this works seamlessly every time you boot Slackware:

1. **Keep the system service disabled:** Do not execute `/etc/rc.d/rc.pulseaudio start` as root. Leave system-wide PulseAudio stopped.
    
2. **Let XFCE manage PulseAudio:** Standard XFCE startup scripts will launch `pulseaudio --start` automatically under your user account (`eduardo`) upon login.