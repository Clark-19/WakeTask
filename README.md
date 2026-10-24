# WakeTask — Your time, your terms

**A little prompt. A real action.**

WakeTask is a browser-based alarm and action-prompt prototype. Alarms can require a small mission before normal dismissal, while clock, timer, stopwatch, and bedtime tools support everyday routines. The name connects the initial prompt with the task that follows it.

## Included
- Alarm list with add/edit/delete, labels, repeat days, volume, sound preview, optional custom audio, mission selection, and enable/disable controls
- Next-alarm card with countdown, selected mission, and a practical preparation tip
- Missions for movement, pose-estimated squats, push-ups, stretching, hydration, breathing, trivia, visual object detection, microphone loudness, mental math, a runnable code lab, memory, typing, QR scanning, reaction, and word scramble
- Thirteen synthesized ringtone-style melodies, including Sunrise, Digital Cascade, Soft Piano, Bright Bells, Arcade Rise, Radar Sweep, Woodblock, Classic Bell, Morning Chime, Double Beep, Deep Pulse, Bright Rise, and Soft Arpeggio
- Five-second emergency bypass with visible hold progress and a confirmation step
- World clocks, countdown timer, stopwatch, and bedtime planner
- Installable PWA shell with local alarm/city storage migration from earlier prototype names

## Run locally
1. Extract the folder.
2. Open a terminal in the folder.
3. Run `python -m http.server 8000`.
4. Visit `http://localhost:8000`.

Camera and microphone access generally require `localhost` or HTTPS and user permission. QR scanning uses a CDN library and needs an internet connection unless the library is stored locally. The Code Lab previews HTML in the browser; Python, C, and JavaScript use the external Piston execution API and require internet access. External compiler availability can vary.

## Important limitations
This is a **working browser prototype**, not a release-ready alarm app or a built APK. Alarm checks only run while the page is open; ringing is not guaranteed when the browser is closed or the phone is locked. The service worker does not provide a dependable scheduled alarm. Dependable background alarms require a native Android app with alarm scheduling, notification/exact-alarm permissions, alarm audio, and reboot rescheduling implemented and tested on the target phone. No native Android or Windows project was included in the supplied ZIP, so this update does not claim to provide a working locked-phone alarm or a built APK/installer. The microphone mission measures loudness rather than recognizing words. The movement challenge pauses when frame motion is not detected. Squat counting uses a browser-side pose model and knee-angle thresholds; camera angle, visibility, and clothing can still cause missed or incorrect counts. The Find the Object mission uses a browser-side COCO-SSD model and only recognizes supported common categories; it can miss objects or misclassify them. Camera models are downloaded from a CDN on first use, so internet access is required. Camera frames are processed in the browser, not intentionally uploaded by this app. These are prototype-level estimates, not medical-grade or guaranteed recognition.

## About the name
**WakeTask** combines *wake up* with *task*: the alarm is the cue to get up, and a small mission turns that cue into an action. The product is designed around the idea that starting an intended action should be more than tapping a button.


## Recent interface updates

- Added a categorized Mission Center with Exercise / Conditioning, Logic & Brain Training, and Quick Action Challenges.
- Added lightweight CSS-only animated mission illustrations (no 3D assets or external image files).
- Added a manual-count push-up challenge, four-operation arithmetic questions (addition, subtraction, multiplication, division), and a language chooser for beginner C, Python, HTML, and JavaScript questions.
- Simplified custom ringtone messaging and added mobile dialog overflow safeguards to prevent horizontal swipe blank space.
- The camera-based missions still depend on browser permissions, HTTPS, and external model/library downloads where applicable.


## Update notes (2026-10-24)
- Stabilized the Brain-Melter Math and QR Code Sprint illustrations so they do not float or bounce.
- Replaced the short mission summary with a nested mission-detail panel showing objective, steps, estimated duration, verification, equipment, permissions, completion rules, safety, and outcome. Details change with the selected mission.
- Added an explicit Browse button for the audio picker, file-type and size validation, selected filename feedback, selection preview, and a saved-sound preview action.
- Added six original synthesized ringtone patterns (13 built-in choices total).
- Tightened time-input sizing and branding-icon sizing for narrow screens.
- Logo limitation: the supplied archive contains `icon.svg` and an inline header mark, but no separate original logo source file. The header now uses the shipped icon asset; if a different official logo is intended, its original asset must be supplied rather than guessed.
- The app still checks alarms in the active page only. Android locked-screen/background scheduling is not implemented by this web-only ZIP and must not be assumed to work.


## Follow-up audit notes
- Stored alarms are normalized on load to protect against malformed legacy browser data.
- Alarm save is guarded against rapid duplicate submission. Code Lab requires a successful run (or a loaded HTML preview) before completion.
- QR Code Sprint includes a manual confirmation fallback if camera scanning is unavailable. This fallback is explicitly not scanner-verified.
- If custom ringtone playback fails, the selected built-in tone is used as a fallback.
- The supplied project archive has only `icon.svg`; no separate official WakeTask logo source was found. The header sizing was adjusted, but the true logo cannot be accurately restored until its original asset is supplied.
