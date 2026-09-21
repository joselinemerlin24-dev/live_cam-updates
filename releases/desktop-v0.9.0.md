# LiveCam 0.9.0

Released 2026-09-21.

A new look, a current voice engine stack, and the corrections found by the
release review: file conversion, cloud voice training, the video component on
a fresh computer, and a start refused right after a settings change.

### Added

- The home page tells you when a newer LiveCam is available, with a
  button that takes you to the update. LiveCam now looks for releases on
  its own after it starts and every few hours, so you no longer have to
  open the settings to find out. Closing the notice hides it until the
  next release.

### Changed

- The voice engine's software stack moved to current releases (Python
  3.14, current PyTorch with CUDA 13, numpy 2, and current audio and web
  libraries). Two unmaintained libraries the trained-voice content model
  and the noise cleanup depended on were replaced by maintained
  equivalents or small in-house ports, with equivalence checks against
  the previous versions. Voice quality is unchanged on the reference set.
  This release republishes the backend runtime, so the first start after
  the update downloads it again.
- La voix suit mieux la hauteur naturelle de la personne qui parle,
  surtout sur les voix calmes. La vérification du micro écoute la phrase
  jusqu'au bout pour y arriver: comptez une dizaine de secondes.
- LiveCam has a new logo. It appears on the window, the taskbar, the Start
  menu shortcut, the installer, and inside the app.
- The "Look" preview (clothing and hairstyle on your photo) now runs on a
  newer image editing engine that keeps the person more faithful and
  follows the requested change more precisely.
- The window's top edge is one row. The logo, the name, the pages, the
  guided tour, and the window buttons share it, instead of a system title
  bar stacked over an in-app header that repeated the same logo and name.
  Drag anywhere on the row to move the window; double-click it to
  maximize.
- The name beside the logo is set as a wordmark: "Live" heavy, "Cam"
  light, in one ink. The setup and licence screens use the same mark.
- On the Voice page, the selected voice's name and the "En direct /
  Fichier audio" switch now stay put at the top of the stage, on the same
  column as the content under them. Switching modes only changes what is
  below the switch; the name no longer moves up or down with the height of
  each mode. The stage column is wider, and its content starts at the top
  instead of floating in the middle of the pane.
- A new look for the controls. Buttons, switches, pickers, and fields are
  drawn with fine lines and a light from above, so anything you can press
  stands slightly off the page and anything you type into sits slightly
  into it. Cards and dialogs are flat. Depth no longer comes from soft
  shadows. The app ships its own typeface, so text looks the same on every
  computer. Layouts and the placement of every control are unchanged.

### Fixed

- Converting a file that cannot be read (a damaged recording, for example)
  now reports the problem right away and frees the voice engine. It used to
  stay on "conversion in progress" for minutes, and the next conversion
  answered that one was already running, until you cancelled by hand.
- Creating or upgrading a voice with full training works again on a fresh
  cloud machine. A missing file in the training environment made every such
  job stop at 5% without reporting an error; the previous instant voice
  stayed usable, but the trained one never arrived.
- The installer now installs the system component the video engine depends
  on when the computer does not have it, so the face features work on a
  freshly set up Windows. Computers that already have it are left untouched;
  uninstalling LiveCam leaves it in place because other programs may use it.
- Changing a voice setting (latency mode, clear speech) while the voice was
  being prepared could make the next start answer "La voix est encore
  occupée" once, until you tried again. The start now waits the fraction of
  a second the preparation needs to finish, then goes on.
- A file conversion started on the voice page now keeps running when you
  visit another page, and its result waits on that voice when you come
  back (a notice says so if it finishes while you are elsewhere). Leaving
  the page used to abandon the conversion, and the next attempt then
  reported one already in progress. While a conversion runs, starting the
  live voice or the microphone preview asks you to wait for it or cancel
  it, and file conversion waits while the live voice is on, so two voice
  engines never run against each other.
- Unplugging or switching the sound output (Bluetooth earphones dropping,
  for example) while a voice preview is loaded no longer freezes the whole
  app on the next play or scrub. The preview forgets the lost output and
  plays through the current one. The same guard now covers a clip kept on
  a network drive or a cloud folder that stops answering: the app waits a
  short bounded time, then gives the clip up instead of freezing.
- Restarting the voice engine, or a video worker that stopped answering,
  no longer freezes the window for the seconds the old process takes to be
  stopped.
- Saving a support report to a slow or disconnected network location no
  longer freezes the window while the file is written.
- A voice engine that is still running but has stopped answering is now
  noticed within about a minute: LiveCam stops it and offers the restart,
  instead of leaving every indicator green until you relaunch.
- If the licence check refuses to start the voice engine at launch (a file
  briefly held by another program, for example), the setup screen now says
  so with a retry, instead of the app staying on its start screen forever.
- An audio file with a damaged header (a recording that was never finalized,
  for example) no longer closes LiveCam outright when you add it as a voice
  sample or pick it for conversion. It is reported as unreadable instead.
- If LiveCam cannot open its window at launch (a display session without
  graphics acceleration, a graphics driver being reinstalled), it now says
  so in a message instead of closing with nothing on screen.
- If the licence check moves you off the face page while a look is being
  composed, the other pages no longer stay locked behind "Navigation
  verrouillée" until you relaunch.
- A face whose photo can no longer be read, or a video worker that cannot
  start, no longer makes LiveCam retry the face push in a tight loop at
  every launch (which also kept relaunching the worker and could leave a
  look application spinning). The push is retried when you act on it or
  when the engine comes back, and going live answers instead of hanging.
- On a first install where the voice engine takes longer than expected to
  answer (a slow disk with antivirus scanning the fresh files), LiveCam now
  keeps the installed engine and simply tries again at the next launch,
  instead of deleting it and repeating the same long install every time.
  The next launch really does find it: the leftover install bookkeeping no
  longer undoes the kept files on startup.
- Two slow starts in a row no longer trigger a full re-download of the
  voice engine. Only a real failure counts toward that repair.
- "Quitter et supprimer" now also works while the engine is being verified
  or unpacked, instead of only during the download.
- An unplugged camera now ends the video within a second instead of after
  about twenty seconds of showing the last picture.
- While the instant voice engine downloads on a fresh install, LiveCam no
  longer stacks up status requests on the engine it is waiting for. Closing
  and reopening the add-voice window while that check is still running no
  longer leaves it on "Vérification…" for good.
- The automatic pitch that follows your natural range now also applies
  when the voice was prepared ahead of time, which is the usual case when
  you pick a voice and then go live. Those sessions were starting with no
  pitch adjustment at all.
- Pressing Stop while the live voice is still closing a lost headset can no
  longer let a device refresh restart the audio system underneath that
  close, which could crash the voice engine.
- A voice engine restart launched while the app was already stopping a
  stalled engine can no longer have its new engine stopped by mistake.
- A voice's sample clip that failed to load while the engine was restarting
  is now fetched again, a few seconds apart, instead of showing as
  unavailable for the rest of the session.
- If the computer's clock is set ahead, activating a licence now says the
  clock is off instead of reporting the licence as expired.
- A library written by a newer LiveCam (after installing an older version
  over it, or importing an archive from a newer one) keeps its voices. A
  voice whose state this version cannot read says so on its page, with the
  update one click away, instead of presenting itself as ready; renaming
  it keeps its state exactly as the newer version wrote it. Nothing is
  moved aside. When a truly damaged entry does have to be set aside,
  LiveCam now says so once instead of the voice silently disappearing.
- Pressing Stop while the live voice is recovering from a lost headset no
  longer closes the same audio device twice, which could crash the voice
  engine. Each device is now closed exactly once, by whichever side reaches
  it first.
- Leaving the microphone check while the microphone is being unplugged no
  longer freezes the voice engine's other requests for the seconds the
  device takes to release. The check hands its cleanup to its own thread.
  Closing the check in its first seconds no longer pauses the voice engine
  for five seconds either.
- Cancelling a voice whose training had just finished now really drops it.
  The cancel used to be acknowledged while the next refresh quietly started
  installing the voice again, download after download, until it appeared in
  the library anyway.
- When LiveCam exits without a clean shutdown, the video worker now ends
  its cloud face session and publishes its final safe frame instead of
  leaving the last picture on the virtual camera until the process is gone.
- Face swap no longer stays black when the face is small in the picture,
  as with a wide-angle webcam at desk distance. The video protection that
  waits for a face before showing anything uses a stronger face detector
  that reads faces at that size, in dim rooms and against bright windows,
  and each check costs less than before. Support reports sent from the
  settings include the video protection's state, so a face problem can be
  diagnosed from a report.
- After an update installs, LiveCam opens again by itself instead of
  leaving the desktop empty.
- The first launch after an update no longer ends on a file verification
  error when the licence check and the engine update refresh the licence at
  the same moment.
- While an update is being installed, the settings screen says that the
  download is complete and that Windows will ask for consent, instead of
  showing a full bar under "Téléchargement".

---

The installer above is the only file to download; the source archives are GitHub's automatic copy of this note.
