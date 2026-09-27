# LiveCam 0.10.0

Released 2026-09-27.

Photo preparation for new faces, a setting for face detection, one update for
the app and its engine, and a long list of corrections found by using LiveCam
from its installation to the end of a call.

### Added

- Photo preparation when adding a face. After you choose a photo, LiveCam
  re-takes it as a clean portrait with soft, even light and a neutral
  background (about 40 seconds), then shows both side by side so you keep
  the one that looks most like you. The live face takes on the photo's
  lighting and colours, so a photo taken under coloured or warm light no
  longer tints your face on camera. If the preparation fails, you can try
  again or continue with your own photo.
- "Détection du visage" in the advanced settings, off by default, including
  after an update from an earlier version. Turned on, the live video pauses
  on a still image, then goes black, when nobody is in front of the camera,
  as earlier versions always did. Turned off, the transformed video keeps
  playing when you step away, and the camera image itself is still never
  shown. The change applies right away, even during a live session. To get
  the pause back, turn it on in Paramètres, under "Paramètres avancés".
- A warning when a voice made from a recording shorter than five minutes
  seems to hold more than one person talking. The voice may blend them, so
  the warning offers to pick another recording or keep this one, and it
  stays until answered, even across restarts. It says before you choose
  that picking another recording removes this voice.

### Changed

- Each LiveCam update now brings its own engine: there is one update per
  release instead of an app update followed by a separate engine update, and
  the settings no longer offer an engine update on its own. The first start
  after an update may download the new engine before LiveCam is ready. The
  engine downloads from the same servers as the rest of LiveCam, so it is
  faster on slow connections and no longer stalls when a download link
  expires. An update that brings a new engine removes the previous one
  before downloading, so it no longer stops for lack of disk space that the
  old engine was still taking up.
- Interrupted downloads now continue where they stopped instead of starting
  over: LiveCam updates, voices, and the files for instant voices. A brief
  connection drop, for example when the computer wakes from sleep, no longer
  fails a LiveCam update or the instant voice files: LiveCam waits for the
  connection to come back and tries again. A new version of a voice that is in use during a call is put
  in place shortly after the call ends, without downloading it again.
- The progress of a new voice now matches the real wait. While the online
  service gets ready, LiveCam says it is waiting instead of showing a frozen
  5 %. After that the bar moves steadily through every step, the time left
  shows from the first minutes, and the messages say plainly what is
  happening at each step.
- On a computer that cannot use a voice live, the voice creation dialog no
  longer offers to create a fully cloned voice anyway, and no clone is spent
  on a voice that could never be used there. It says why: the computer has
  no suitable graphics card, its graphics driver needs an update (then
  restart LiveCam), or its graphics card is too old for the live voice.
  Going live and "Tester ma voix" give the same reason.
- Fewer, shorter notifications. Stopping a call and hiccups that fixed
  themselves (sound back, video answering again, face change restored,
  audio adjusted) no longer pop up a message: the screen already shows
  the result. Long messages were cut to one sentence with the next step, words like
  "aperçu" or "voix convertie" were replaced with plain ones, and
  deactivating the licence shows one message instead of two.
- Notifications now appear where they belong instead of all popping up
  in the same place. A problem that concerns the whole app (the voice
  service stopped, a voice test that did not stop) shows as one line
  under the title bar with its button, and stays until it is resolved.
  What happens during a call (a video coming back, a microphone the
  meeting app does not use, a silent microphone) is written under the
  live status while it lasts, and a camera that could not start is
  explained on the camera row. Everything you do that changes something
  is confirmed in a few words in the corner for three seconds, even when
  the result is also visible on the page: renaming, deleting, choosing a
  face or a voice, adding or cancelling a voice, applying a Look,
  resetting, finishing the device setup ("Voix renommée", "Visage
  supprimé", "Paramètres réinitialisés", "Rapport envoyé"). These lines have their own look, set apart from the
  rest of the text by a soft colour and a small dot: brick for a problem
  to fix, ochre for something under way, neutral for information.
- When the voice cannot keep up during a live session, one notice now says
  so instead of two, and only when the sound actually reaches your call
  with gaps. It names the app to close when one is found, and otherwise
  suggests closing a few applications. Meanwhile the quality indicator says
  the quality is reduced instead of protected, and a short message after
  the call says how long the quality dropped. A rare isolated gap does not
  count.
- "Réactivité maximale" in the advanced settings now offers three choices:
  Automatique (the default: the app decides, as before), Toujours, or
  Jamais. Jamais keeps the standard voice delay on computers where the app
  would otherwise lower it on its own. A setting that was on becomes
  Toujours; one that was off becomes Automatique, which is what off already
  did.
- Choosing a face is confirmed right away, without starting the video engine
  in the background. A photo that cannot be used is reported when you go
  live, or when you apply a Look during a live session. The "Réessayer"
  button on the face selection error is gone: choose the face again instead.
- "Tester ma voix" no longer keeps you on the voice page: going to another
  page stops the test. When a test cannot confirm that it stopped, a notice
  with a "Réessayer l'arrêt" button appears on whatever page you are on.
  The microphone meter during the test updates once per second.
- Voice clips on the voice page now play and pause from their play button;
  the waveform shows the progress but no longer jumps to a point when
  clicked or dragged.
- During a live session, a video that stops responding is flagged after about
  10 seconds instead of about 30, and the app checks on the session with
  fewer background requests.
- While offline, moving the computer's clock backwards no longer locks
  LiveCam, as long as the clock stays after the last time LiveCam checked
  its licence online (at each start and every few hours while connected):
  the time LiveCam can be used offline follows the computer's clock. A
  clock set before that check still asks to fix the date and time, as does
  a clock that is off while online.
- When the licence does not allow something, the message now says so. A
  licence whose face service is switched off asks you to contact the
  administrator of your licence instead of suggesting a connection problem,
  and a Look refused because the licence is revoked, suspended or expired
  says so instead of a generic licence line.
- The face photo used for live video is no longer copied to a cache on
  disk: it stays in memory while LiveCam runs, and copies left there by
  earlier versions are deleted.
- LiveCam now tells the online service how long each live face session
  actually streams, about once a minute and once more when it ends, so the
  usage recorded for a licence is measured. Nothing about the video changes.
- The face library now shows the same message as the voice library when it
  cannot be loaded. The confirmation and naming dialogs, the voice page's
  notices, and the guided tours each share one layout across the app.

### Removed

- Library export and import in the settings. Faces and voices stay on the
  computer where they were created; to use a voice on another computer,
  create it again there. Library files saved with earlier versions can no
  longer be opened.
- Audio file conversion on the voice page, with its noise reduction option.
  LiveCam now transforms your voice live only, and the voice page no longer
  switches between a live mode and a file mode.

### Fixed

- The live face no longer stops after about five minutes of a call: one
  face connection now runs for up to four hours, and a face that the
  service ends after a long call reconnects on its own within a few seconds
  instead of leaving the call black until you restart. While the face is
  interrupted or reconnecting, the live screen says so under "Vous êtes en
  direct" instead of showing the video as live, and the message no longer
  blames your face.
- Going back to the dashboard during a call no longer cuts the call's
  video. After the first two minutes of a call, opening another page and
  coming back could end the video with "La caméra ne répond plus",
  although nothing was unplugged. LiveCam now leaves the camera the call is
  using alone when it looks at the cameras again.
- Quitting the setup after reinstalling LiveCam no longer deletes your
  voices and other saved data: it removes only what the setup downloaded.
- Uninstalling LiveCam now completes. From an administrator account it used
  to stop with "Le moteur LiveCam n'a pas pu être supprimé" every time,
  leaving LiveCam listed in Windows' apps with its large engine folder still
  on disk; the engine is now removed with the app. With a meeting open in a
  browser it stopped with "Certains fichiers LiveCam n'ont pas pu être
  supprimés"; the camera files the browser still holds are now removed at
  the next restart, and the uninstall says so.
- The installer and the uninstaller show their French messages with the
  right accents. They used to show garbled letters such as "rÃ©essayez" in
  the message asking to close LiveCam, in several error messages, and on
  the uninstaller's page about deleting your data.
- Windows no longer shows a security alert asking to allow LiveCam on the
  network the first time you go live with your face. The installer now sets
  this up, and LiveCam still accepts no incoming connections.
- LiveCam no longer stops at "Le moteur de LiveCam n'a pas pu démarrer" on
  every start after it was once opened with "Exécuter en tant
  qu'administrateur" and used with an instant voice.
- On a computer where a shared system component, often installed by other
  programs, was older than the version LiveCam ships, "Détection du visage"
  stopped every live session from starting, and reinstalling did not help.
  The installer now updates that component when it is older, not only when
  it is missing. If face detection still cannot start, the app says so and
  names what to do.
- When another application (a meeting app, the Windows Camera app) is using
  your webcam, it stays in the camera choice, greyed, with "Utilisée par une
  autre application", and going live asks you to close that application,
  instead of saying there is no camera or quietly switching to another
  camera. As soon as that application lets the camera go, you can choose it
  and go live.
- With "Synchronisation complète" on, the live video in a call with face
  and voice keeps its full fluidity. It used to show about half the images
  and freeze for close to a second several times a minute; it now only
  waits the time needed to line up with the voice. A call with the face
  alone, started shortly after one with the face and the voice, no longer
  keeps that call's video delay of about a second, and the delay goes away
  when the voice stops during a call. The option's description no longer
  tells you to keep it on, which it is not by default: it says when turning
  it on helps.
- A meeting app no longer warns that LiveCam's microphone is muted by the
  system when it was muted in the Windows sound settings. The sound always
  went through, but the warning sent people to their settings; LiveCam now
  turns that microphone back on when you go live with your voice.
- During a call, the camera choice and the voice switch on the dashboard
  are locked, and so is the face switch when the call started without
  video, each with a line saying to stop the call to change it. Changing
  them there never reached the call, yet the dashboard and the preview then
  showed the change while the meeting still got the old camera, voice or
  video. The preview's camera badge is now in French.
- Voice settings now reach the call. "Correspondance", "Hauteur" and
  "Clarté" on the Voix page change the voice of a live session right away;
  a change used to be saved but only reached the call at the next start.
  Switching to another voice during a live session keeps a pitch or voice
  match you set yourself, and works out automatic pitch again for the new
  voice; the new voice could run several tones too high or too low.
- "Tester ma voix" now sounds like the call: it uses the same automatic
  pitch, voice range, and voice match as going live, and every change to
  the voice settings made while listening applies without restarting the
  test. It says when automatic pitch could not be set for your microphone,
  as going live already did, and on a voice whose files are no longer on
  the computer it downloads them again instead of promising a download
  that never started.
- The microphone check now measures your voice, so automatic pitch works.
  In the installed app the measurement never started: every check ended
  with "Le réglage automatique de la hauteur est indisponible pour le
  moment", and every go-live asked you to redo the check, which could not
  help. When automatic pitch cannot be set for a reason a new check cannot
  fix, the go-live message now suggests setting the pitch by hand instead.
- When the local LiveCam service stops unexpectedly, the restart it offers
  now works during a live session: the camera keeps running, and LiveCam
  then says to stop and start the session again to get the voice back. The
  voice shows as stopped right away instead of still looking live for up
  to a minute and a half. Closing the restart notice no longer leaves
  LiveCam stuck saying it is still starting: going live, the voice pages
  and the device check bring the restart back. The microphone check no
  longer says no microphone was found, or forgets the one you checked; it
  offers the restart and lists your devices again once the service is back.
  When a restart cannot run, LiveCam says why.
- When LiveCam must be updated before it can continue, "Mettre à jour" now
  works even while a voice is being created: the voice keeps being made on
  LiveCam's servers and picks up where it left off after the update. Only a
  voice recording that is still being sent holds the update back, in
  Settings too, and LiveCam says so instead of asking to finish an action
  that is not shown or not running. When the update is needed during a
  live session, the session stops before the update screen shows, and the
  update can be installed right away.
- When LiveCam stayed open without internet past the 72 hours it can run
  offline (for example a laptop asleep for several days), the dashboard now
  says the licence needs checking as soon as that time is up, and going
  live checks the licence online right away, so it works on the first try
  once you are connected. It used to show the licence as fine and keep
  asking to reconnect for up to ten minutes.
- When the licence stops being valid while the app is open (for example a
  revoked or paused licence), the licence screen now stays up until the
  licence is valid again. Opening the dashboard or the settings at that
  moment could briefly bring the app back, with a "LiveCam a rencontré un
  problème" message whose restart did nothing.
- Settings no longer says the licence will be checked at the next internet
  connection while you are online and the licence was just confirmed. The
  line shows only when the licence has gone several hours without an
  online check.
- A voice that finishes creating while LiveCam stays closed for more than
  seven days is no longer charged. Created voices stay online for seven
  days; one that never reached your computer in that time now gives the try
  back, and its card says the voice was ready but could not be picked up in
  time. A voice that did reach your computer and was later lost says its
  online copy expired, instead of claiming the creation failed and was not
  counted, and relaunching a voice says when it counts as a new creation.
- Creating or upgrading a voice without an internet connection said the
  voice creation had failed. It now says the online service could not be
  reached and asks you to check your connection, including when the
  connection drops while a long recording is being sent. A voice whose
  upload was cut off by closing LiveCam shows as interrupted as soon as
  LiveCam restarts, instead of after about half an hour.
- When upgrading a voice to full cloning fails because its recording is not
  clear enough, the message no longer asks to retry with a clearer
  recording, which an upgrade cannot take. It suggests creating a new voice
  from a clearer recording, and still says the voice stays usable.
- A voice you removed while it was still being prepared no longer comes
  back later as a finished voice, and a stop pressed just as a voice
  finished keeps the finished voice. A voice whose files another program
  still held when you removed it stays listed and followed. Adding a second
  voice with the same name as an existing one now says so.
- When a voice cannot be prepared on this computer, LiveCam says why right
  away and stops trying, instead of rebuilding the voice again and again
  for three minutes and then saying the preparation was slow. Picking
  another voice or going live tries again. A voice that takes more than a
  few minutes to get ready for a live session is no longer cancelled while
  the computer is still preparing it: LiveCam waits as long as the voice
  allows, says it needs a little more time, and still stops a start that
  really fails. A live session that takes unusually long to start is no
  longer abandoned after nine minutes.
- When LiveCam loaded correctly but could not finish starting because of
  something on the computer, it said its files might be damaged, offered a
  large repair download that could not help, then blamed the antivirus. It
  now says LiveCam could not start on this computer and suggests restarting
  it or writing to support. Long messages on the installation screen wrap
  inside the card instead of running past the edges of the window.
- A repair of LiveCam's files that starts without an internet connection
  now says to check the connection, and the next start with a connection
  repairs the files. It used to count as done though nothing was
  downloaded, and every later start blamed the antivirus until a full
  reinstall.
- Installing LiveCam's engine no longer fails, and no longer throws away the
  finished download, when security software briefly checks one of the new
  files at the last step. If another program keeps a file longer, the
  message says so, and trying again reuses the download.
- Clearer messages when going live fails. The microphone or audio output
  that cannot be opened now comes with a suggestion to close the apps that
  may be using them, instead of saying the device is not available on this
  computer. A failure LiveCam cannot name says the live session could not
  start and suggests trying again, then restarting LiveCam, and says when
  the local LiveCam service is not running. A camera list that could not
  be read no longer reads as "no camera available". Some errors that
  showed a generic "try again" line now show their own message.
- When the webcam stops working during a live session, for example when it
  is unplugged, the message asks to check its connection before going live
  again, and names the LiveCam camera when that is the one that stopped.
  Installing an update afterwards no longer asks to finish an action that
  is not running. When the microphone or the audio output is lost during a
  call, the message says to stop and restart the call, instead of pointing
  to a voice-only restart that does not exist.
- The live face no longer stays black when the camera sits far from you, as
  with a webcam on a monitor at arm's length or more: a face that is small
  in the frame is now found too, and the paused-picture notice says to bring
  the camera closer. With "Détection du visage" on, going live before your
  face is recognized no longer ends about 30 seconds later with a message
  about your connection: the paused picture stays until your face is
  recognized, and the video then starts on its own.
- When the online face service itself fails, preparing a face photo,
  creating a Look, or going live with a face says the service is briefly
  unavailable and to try again in a few minutes, instead of asking you to
  check your internet connection. When the live face reconnects many times
  in a short while, the app says to try again in two minutes.
- Sending a support report, or opening voice creation for the first time,
  during a call no longer makes your voice stutter for a moment.
- "Réinitialiser les paramètres" is unavailable during a call or while you
  listen to your voice, with a line saying why: a reset there changed the
  dashboard switches and devices under the running call. The confirmation
  says in two plain sentences what a reset does: most options, including
  the microphone, the camera and the voice tuning, go back to their
  defaults, while your faces and voices, and the ones you use, stay as they
  are.
- During the microphone check, "Aucun son ne vient du micro" shows only
  while the microphone is really silent. It used to show after 20 seconds
  even while the level bar moved.
- A call started with the voice only shows the video as off ("Désactivée")
  instead of "en attente", which suggested video was on its way.
- When the Windows system folder cannot be found, repairing the LiveCam
  camera or installing the virtual microphone says so, instead of a generic
  failure.
- The guided tour now keeps each step's highlighted area entirely inside
  the window, scrolling it into view: on a window of the default size, the
  "Démarrage guidé" step left the bottom of its area under the edge of the
  window. The highlight also has clean rounded corners, without a light
  square showing at each corner.

---

The installer above is the only file to download; the source archives are GitHub's automatic copy of this note.
