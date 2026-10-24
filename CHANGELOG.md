# WakeTask revision notes

- Fixed mobile dialog horizontal overflow/sideways blank-space behavior with viewport constraints and vertical touch scrolling.
- Removed the long custom-ringtone explanation; renamed the saved custom-sound action to “Remove custom sound”.
- Added a categorized Mission Center with CSS-only animated graphics.
- Exercise / Conditioning: Jumping Jacks, Squats, and Push-up Challenge.
- Logic & Brain Training: Math, Code Detective, Memory, Typing, Reaction, and Word Scramble.
- Quick Action Challenges: Voice Energy, QR Code Sprint, and Find the Object.
- Math now supports addition, subtraction, multiplication, and division.
- Code Detective now requires the user to select Python, C, HTML, or JavaScript before seeing a question.
- Push-up Challenge uses a manual rep counter and clearly says that it does not verify form automatically.
- Updated the service-worker cache version so updated files can replace the previous cached build.

## Responsive and mission update
- Replaced generic mission symbols with recognizable, purpose-matched SVG illustrations for exercise, math, coding, memory, typing, QR, hydration, breathing, and other tasks.
- Centered the saved custom-sound status and the “Remove custom sound” action.
- Reworked the fixed bottom navigation sizing and spacing to stay within narrow mobile screens and scale on wider screens.
- Updated the header to show “WakeTask” only and refreshed the app icon to match the graphic brand mark.
- Added Stretch Reset, Water Check, Breathing Reset, and Quick Trivia missions.
- Replaced the coding quiz with a small code lab: select Python, C, HTML, or JavaScript; edit starter code; run HTML in a local preview; run Python/C/JavaScript through the online Piston execution API.
- Bumped the service-worker cache to v6 so updated files can replace the previous cached app.
- Validation performed: JavaScript syntax check and HTML parse. Physical-device layout testing and live external compiler availability were not verified in this environment.


## 2026-10-24 — Mission, audio, and responsive fixes
- Disabled float/bounce animations on Brain-Melter Math and QR Code Sprint cards/artwork.
- Added a nested mission information panel with mission-specific steps, permissions, verification, equipment, safety notes, completion rules, and post-completion behavior.
- Added an explicit audio Browse action, supported-type/size checks, filename feedback, selection preview, and saved custom-sound preview.
- Added six synthesized ringtone choices: Classic Bell, Morning Chime, Double Beep, Deep Pulse, Bright Rise, and Soft Arpeggio.
- Switched the header mark to the only shipped icon asset. The supplied archive does not contain a separate official logo file.
- Adjusted time input sizing and small-screen mission detail layout.
- Confirmed browser alarm limitation remains: page-open JavaScript checks cannot guarantee alarms when the browser is closed or the phone is locked.


## 2026-10-24 — Follow-up audit and reliability fixes
- Hardened saved alarm/city loading so malformed or outdated browser storage does not crash the interface; invalid alarm times are discarded and alarm fields are normalized.
- Forced an explicit 24-hour (`00:00`–`23:59`) internal clock format to avoid midnight formatting mismatches in alarm checks.
- Prevented rapid double-submit from creating duplicate alarms and added save-button locking while custom audio is read.
- Added confirmation before deleting an alarm and prevented Escape from hiding an active alarm or closing a mission while its media session is active.
- Added a clearly labeled manual fallback for QR Code Sprint; it explicitly says the fallback is not scanner-verified.
- Code Lab can only be marked complete after a successful run or an HTML preview.
- Custom ringtone playback now falls back to the selected built-in sound if the saved custom audio fails to play.
- Adjusted the supplied icon sizing in the header and bumped the service-worker cache to v7. The original/official logo file is still not present in the supplied archive, so the included icon has not been misrepresented as a verified official logo.
