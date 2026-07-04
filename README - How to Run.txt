PreVision — Solar & Energy Storage Sizing App
==============================================

HOW TO RUN
----------
1. Keep "PreVision.exe" and the "dist" folder together in the same folder
   (don't separate them — the app reads its files from "dist").
2. Double-click "PreVision.exe".
3. A black console window opens and your default browser opens
   automatically to the app. If the browser doesn't open by itself,
   go to: http://localhost:3000

4. To close the app, close the black console window.


ABOUT THE "WINDOWS PROTECTED YOUR PC" WARNING
----------------------------------------------
Because this .exe wasn't signed with a paid Windows code-signing
certificate, Windows SmartScreen may show a blue warning screen the
first time you run it. This is normal for independently-built software,
not a sign that anything is wrong. To proceed:

  Click "More info"  ->  then click "Run anyway"

Windows only asks this once per file.


INTERNET CONNECTION
--------------------
PreVision itself runs entirely on your PC. It only reaches out to the
internet for one thing: looking up solar/weather data (PVGIS, NASA
POWER, Open-Meteo) for the location you enter. If you're offline, you
can still use the app by typing coordinates manually or using the
built-in offline default climate values.


TROUBLESHOOTING
----------------
- "Could not find a free port": something else on your PC is using
  ports 3000–3019. Close the other app, or restart your PC, then
  try again.
- Nothing happens when you double-click: right-click PreVision.exe ->
  "Run as administrator" isn't required, but try it once if Windows
  is blocking it silently.
- Antivirus flags it: this can happen with any unsigned .exe built
  outside an app store. The full source code is in the "source"
  folder if you'd like to inspect it or rebuild it yourself
  (see source/BUILD.txt).


WHAT THIS EXE ACTUALLY IS
---------------------------
A small native Windows program (no Node.js, no installer, no
dependencies) that serves the PreVision web app on your machine and
opens it in your browser. All of the sizing calculations, charts, and
PDF export run locally in the browser exactly as they do in the
original web app.
