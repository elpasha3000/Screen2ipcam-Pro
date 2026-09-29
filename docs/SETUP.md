# Screen2ipcam Pro setup guide

[Back to the overview](../README.md) · Online version: [screen2ipcam.com/pro/guide](https://screen2ipcam.com/pro/guide)

## Quick start

1. **Install** Screen2ipcam Pro from the [Microsoft Store](https://apps.microsoft.com/detail/9P8T6K6GWR87) on the PC or POS whose screen you want to record.
2. **Open it** from the Start menu and press **Start my free trial**. The trial needs an internet connection.
3. **Note the PC's IP address** on the **Status** tab, for example `192.168.1.50`.
4. **Add it to your recorder** with ONVIF search, or manually with the IP, port `8000` and login `admin` / `admin`.
5. **Change the password** on the **Users** tab once it works.

> The PC and the recorder must be on the same local network. The video goes straight from the PC to your recorder and never passes through our servers.

## Connection details

| Setting | Default |
|---|---|
| ONVIF port | `8000` |
| RTSP port | `554` |
| Main stream (recording) | `rtsp://PC-IP:554/screenlive` |
| Sub stream (live view) | `rtsp://PC-IP:554/screensub` |
| Web control panel | `http://PC-IP:8080` |
| Default login | `admin` / `admin` |
| Video | H.264, main stream and sub stream |

Replace `PC-IP` with the address on the Status tab. You can change the ports on the Network tab.

## Add it to your recorder

**Hikvision**
1. Configuration, System, Camera Management.
2. Add, protocol **ONVIF**.
3. PC IP, port `8000`, user and password.
4. Save. The screen appears as a new channel.

**Dahua**
1. Camera, Registration, Device Search, or Manual Add.
2. Choose **ONVIF**.
3. PC IP, port `8000`, user and password.
4. Apply, check live view, then turn on recording.

**Blue Iris**
1. Add camera, Network IP.
2. Find/Inspect with ONVIF, or make ONVIF.
3. PC IP, ONVIF `8000`, RTSP `554`, user and password.
4. Main stream for recording, sub stream for live view.

**XMEye, Uniview and others**
Use ONVIF search or manual ONVIF add with port `8000`. If your recorder or VMS asks for an RTSP link, use the main stream link above.

It also works with Synology Surveillance Station, Milestone, Agent DVR, Frigate, VLC and other ONVIF or RTSP software.

## For POS and cashier PCs

- Put the POS channel next to the counter camera in your recorder's layout, so playback shows both at the same time.
- Turn on the camera name and the date and time on the **Stream extras** tab, so every recording shows which till it came from.
- Turn on the **Video Loss** alarm for this channel in your recorder. If the stream ever stops, the recorder tells you at once.

## Record only when the screen changes

1. On the **Events** tab, turn on motion detection and save.
2. In your recorder, set the Screen2ipcam channel to record on motion (event) instead of continuous.
3. Change something on the screen and check that the recorder marks a motion event.

## The control panel

| Tab | What it's for |
|---|---|
| Status | Streaming on or off, and the PC's IP address |
| Video | Which monitor to stream and the picture quality |
| Network | ONVIF, RTSP and web panel ports |
| VPN | Choose the right network address when the PC also runs a VPN |
| Stream extras | PC sound, and the camera name and date/time on the picture |
| Events | Motion detection that tells your recorder when the screen changes |
| Users | Change the login name and password |
| License | Trial days left, plans, and Restore purchase |

You can also open the panel from any browser on your network at `http://PC-IP:8080`.

## Troubleshooting

**The recorder can't find the PC**
- Check both are on the same network.
- Add it manually with the IP and port `8000`.
- If the PC runs a VPN, pick the local address on the VPN tab.
- If you use a third-party firewall, allow ports 8000, 554, 3702 and 8080.

**Found, but no picture**
- Check the login in the recorder matches the Users tab.
- Make sure streaming is on in the Status tab.
- Try the RTSP main stream link in VLC on another PC.

**The trial says it needs internet**
The trial checks in with our server. Connect the PC to the internet, then open the app again.

**Streaming paused**
The trial ended. Choose a plan on the License tab, or press Restore purchase if you already bought one.

**Still stuck?** [Open an issue](../../../issues/new/choose) or email support@screen2ipcam.com, and tell us your recorder brand.
