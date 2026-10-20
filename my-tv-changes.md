# My TV changes (Redmi TV 5A 32, 192.168.1.30)

Free memory before: 317 MB free / MemAvailable 201 MB (2026-10-20)

## Apps turned off (2026-10-20)

Undo one: `adb -s 192.168.1.30:5555 shell pm enable <package>`

- `com.miui.tv.analytics` off. Undo: `adb -s 192.168.1.30:5555 shell pm enable com.miui.tv.analytics`
- `com.xiaomi.statistic` off. Undo: `adb -s 192.168.1.30:5555 shell pm enable com.xiaomi.statistic`
- `com.google.android.tvrecommendations` off. Undo: `adb -s 192.168.1.30:5555 shell pm enable com.google.android.tvrecommendations`
- `com.mitv.tvhome.mitvplus` off. Undo: `adb -s 192.168.1.30:5555 shell pm enable com.mitv.tvhome.mitvplus`
- `com.xiaomi.mitv.handbook` off. Undo: `adb -s 192.168.1.30:5555 shell pm enable com.xiaomi.mitv.handbook`
- `com.xiaomo.tv.milegal` off. Undo: `adb -s 192.168.1.30:5555 shell pm enable com.xiaomo.tv.milegal`
- `com.xm.webcontent` off. Undo: `adb -s 192.168.1.30:5555 shell pm enable com.xm.webcontent`
- `android.autoinstalls.config.xioami.dangal` off. Undo: `adb -s 192.168.1.30:5555 shell pm enable android.autoinstalls.config.xioami.dangal`
- `com.google.android.play.games` off. Undo: `adb -s 192.168.1.30:5555 shell pm enable com.google.android.play.games`
- `com.google.android.videos` off. Undo: `adb -s 192.168.1.30:5555 shell pm enable com.google.android.videos`
- `com.google.android.feedback` off. Undo: `adb -s 192.168.1.30:5555 shell pm enable com.google.android.feedback`
- `com.android.printspooler` off. Undo: `adb -s 192.168.1.30:5555 shell pm enable com.android.printspooler`
- `com.google.android.tvlauncher` off (by install.sh). Undo: `sh undo.sh 192.168.1.30` (also removes the new home screen), or `adb -s 192.168.1.30:5555 shell pm enable com.google.android.tvlauncher`
- `com.mitv.tvhome.atv` (PatchWall) off. Undo: `adb -s 192.168.1.30:5555 shell pm enable com.mitv.tvhome.atv`

## Installed

- TV Detox home screen (`com.ansub.tvhome`) with YouTube, Hotstar, Prime Video, Sun NXT, VLC. Undo: `sh undo.sh 192.168.1.30` from the tv-detox folder.

## Result

- Restarted once on 2026-10-20: started normally, the new home screen opens, HDMI1/HDMI2 are listed.
- Free memory after: MemAvailable ~265 MB (was 201 MB). The home screen now uses 38 MB (was 122 MB).

## Turn everything back on at once

```sh
for p in $(adb -s 192.168.1.30:5555 shell pm list packages -d | tr -d '\r' | sed 's/package://'); do adb -s 192.168.1.30:5555 shell pm enable "$p"; done
```
