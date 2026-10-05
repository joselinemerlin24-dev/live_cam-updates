# LiveCam 0.11.0

Released 2026-10-04.

A décor behind you in calls, looks you can describe in words, calls that
start without waiting for your face and keep it through network trouble, a
reorganised Paramètres, and many corrections found by testing LiveCam from
its installation to the end of a call.

### Added

- A face can now have a « Décor »: the place shown behind you during a call,
  described in words or shown with a photo, like the outfit and the
  hairstyle, with or without a look. LiveCam first checks that this computer
  can show a décor fast enough; when it cannot, the panel says so and your
  choices are kept. It then prepares the place once, shows it before you use
  it, then puts it behind you in your calls. The face library names each
  face's décor next to its outfit and hairstyle.
- A décor never shows your room without your choice. If it stops or cannot
  be shown during a call, or the computer becomes far too slow for it, the
  video pauses with your room hidden, and you can continue without the décor
  from the dashboard or from Visage. The next call checks again and shows
  the décor when it can. A call whose décor cannot be put in place does not
  start, and you can try again. A décor saved by a newer version of LiveCam
  is kept for that version.
- The outfit and the hairstyle of a face can now be described in words
  instead of shown with a photo: each one offers « Décrire » or « Photo ». A
  face now keeps what its look is made of: the style panel shows the outfit
  and the hairstyle it wears, and the face's picture in the library and on
  the dashboard shows the look. Reopening an outfit, hairstyle or décor
  description puts the cursor after its text, so what you type adds to it.
- During a call, the video now pauses by itself once no app uses the LiveCam
  camera, and comes back as soon as one does. With « Détection du visage »
  on, it also pauses while nobody is in front of the camera. Your voice
  keeps working, and the live status says when the video is paused and why.
- « Moteur vidéo » in Paramètres picks the version that transforms your face
  live. « Recommandé », the default, follows LiveCam's choice and updates on
  its own; you can also keep a specific generation, and the menu explains
  each choice. If a generation you picked is no longer available, LiveCam
  tells you once and goes back to the recommended version.
- The Voix page shows which voice your calls use, the way Visage shows your
  face: its circle is the one outlined, even while you look at another
  voice, and « Utilisée pour le direct » sits beside its name. A ready voice
  that is not used yet offers « Utiliser pour le direct ».
- The installer now adds the licence notices of the open-source software
  LiveCam is built with, in livecam-open-source-notices.txt in LiveCam's
  installation folder.

### Changed

#### Calls

- Going live no longer waits for your face to connect. Within a few seconds
  the call starts with your voice and a black image while your face
  connects, and LiveCam keeps trying on its own. Only a refused photo or a
  licence or account problem still stops the start, with its own message; a
  slow or unstable connection no longer makes it fail with a request to
  restart LiveCam. This also works during the pause the face service asks
  for after many reconnections: the live status shows when your face comes
  back, up to ten minutes later.
- During a call, the live status says why your face is away and what happens
  next: a connection that drops now and then, no internet connection, the
  face service not answering, a pause after many reconnections with the time
  left, a network that blocks video, or a computer clock that is wrong. When
  LiveCam gets your face back on its own, the status says so and asks
  nothing of you; when it cannot, it says « Vidéo arrêtée » and what to do.
  A freeze of a few seconds no longer makes the status flicker.
- During a connection problem, the call keeps showing the last transformed
  image of your face for up to 30 seconds, instead of 10, before the video
  turns black.
- The face photo sent each time the live face connects is about half as
  large, with the same likeness, so the face comes back sooner after a drop
  on a slow or unstable connection.
- The stop button now reads « Arrêter le direct », like « Démarrer le
  direct », and the guided tour, its invitation on the dashboard and the
  guided start say « Démarrer le direct » instead of « Lancer le direct ».
  The lines that ask you to restart a call use the same words, and a paused
  image is called « Image en pause » everywhere.
- « Où envoyer votre voix » now offers only the output that leads to
  LiveCam's virtual microphone, the one the setup guides your call app to.
  Your speakers, your headset and other programs' virtual audio devices are
  no longer offered or accepted for your calls, where « Démarrer le direct »
  then refused them, and a choice of one saved by an earlier setup is
  forgotten so LiveCam asks again. Devices whose name contains words such as
  "Virtual" or "Cable" can now be chosen in « Écoute du test », and the
  microphones of other programs' virtual devices as your microphone.

#### Voices

- Adding a voice now shows the two ways to clone it side by side, with how
  long each takes, how faithful it sounds and whether it counts toward your
  cloning limit. Before your first face or voice, Visage and Voix no longer
  list "how it works" steps: the drop zone says what to add, including what
  makes a good photo.
- A voice is made only from files that really are one of the offered types
  (WAV, FLAC, MP3, M4A, AAC, Ogg, Opus), recorded at a sample rate from
  8 kHz to 384 kHz. A file of another type renamed to one of them, or an M4A
  file that also holds video or subtitles, is refused as a format LiveCam
  cannot read. Unusual or very long audio files are handled more reliably,
  and a steady background hum in a phone voice memo (M4A, AAC) is now
  pointed out, as it already was for other recordings.
- An instant voice made from a recording longer than five minutes is made
  from its first five minutes.
- When many voices are being prepared at the same moment, or you try to
  create instant voices many times within a minute, LiveCam asks you to wait
  a moment and try again before your files are processed.
- When you send the same recording again before an earlier send of it
  finished, the earlier attempt now says it was replaced by the new send
  instead of interrupted. It is still not counted.
- Voix no longer has a « Réinitialiser » button next to « Actualiser »: one
  click there forgot your checked microphone and call output with no way
  back. Each device can still be changed on its own, and resetting the
  settings in Paramètres still forgets them.
- The note about reduced voice responsiveness during a call now explains
  when LiveCam could not yet tune the voice for this computer, and asks you
  to reconnect to the internet and start the voice again.

#### Faces and looks

- A face photo must now show exactly one person, with the face clearly
  visible and large enough; small faces in the background do not count. A
  photo with nobody on it, with several people of similar size, or with a
  face too small to recognise is refused when you add it, with the reason,
  before it is prepared, and a prepared photo or a new look that does not
  show exactly one face is not offered. Before, such a photo was accepted,
  and a call with it could show your own face or a broken image while
  LiveCam said all was well.
- A face already in your library whose photo fails that check is marked with
  the reason and is never deleted. Going live with it does not start, and
  the dashboard says why under that face for as long as it is chosen. On
  Visage, the reason takes the place of « Appliquer », so no look or décor
  is made from that photo; a face whose look alone was refused can still get
  a new look from its original photo. Add a photo of a single person to
  replace it.
- Looks now add up: changing the hairstyle of a face that already wears an
  outfit keeps the outfit, and every change is applied together with one
  « Appliquer ». Removing every item from a look and applying goes back to
  the original photo without making a new picture.
- The style panel is simpler: the outfit and the hairstyle are two compact
  rows that show what each holds, marked « À appliquer » while changed, and
  open one at a time. While a new look is made, the portrait stays as it is
  with a small wait message, then the new look fades into place, and the
  first press to see the original photo under a look shows it at once. On
  Visage, the live caption says the outfit and hairstyle of the picture are
  used too, the photo size limit reads 25 Mo, the real limit, and faces are
  no longer called « préréglage ».

#### Installation, settings and support

- Closing LiveCam during its first installation now keeps what was already
  downloaded, and the next start carries on from there; only « Quitter
  l'installation » deletes the downloaded files. When that download stops
  partway, the setup screen shows how far it had come instead of 0 %.
- Paramètres has a sidebar with four sections, each with its icon: Général,
  Licence et mises à jour, Avancé and Aide, and it opens again on the last
  one you used. Settings are grouped in cards, with clear names, a short
  line that explains each one and more space between rows, and « Moteur
  vidéo » and « Réactivité maximale » are chosen from a menu that opens at
  once. Resetting the settings and deactivating the licence sit at the end
  of their section as quiet buttons; both still ask before acting.
- « Licence et mises à jour » has one card, with a row for this version and
  a row for the licence, each with its state and its action. A dot in the
  sidebar shows when the licence or an update needs a look, and « Mettre à
  jour » on the dashboard opens that section directly. The update line names
  the new version, « Rechercher » says when LiveCam last looked for one, and
  « Informations techniques » sits under Aide with a button to copy it.
- Text looks the same on every page: titles, section headings, names,
  descriptions and buttons have one size and one weight each, and small
  uppercase section labels are now plain headings. The theme is chosen from
  three pictures of LiveCam (Système, Clair, Sombre) under Paramètres >
  Général.
- The camera, microphone and output pickers on the dashboard and in Voix now
  use the same menu as Paramètres: it opens at once, lines up exactly with
  its field, shows long device names in full, marks the current choice with
  a plain check mark, and a letter jumps to the device that starts with it.
- Support reports now include the recent desktop log, a timeline of the last
  calls' starts, troubles and stops with their causes, and whether the
  licence was last checked online and how long ago. Each message you saw is
  listed once, with its cause and how many times it came back.

### Fixed

#### Calls

- A short internet drop during a call no longer tears down the transformed
  face: LiveCam waits for the connection to come back and the face returns
  on its own a few seconds later, instead of staying frozen or black while
  it reconnects from scratch. After a longer outage, the face comes back on
  its own once the internet returns, usually within about ten seconds. On an
  unstable upload connection, LiveCam waits for the stream to come through
  instead of reconnecting over the same bad link again and again, and a slow
  upload no longer makes a reconnection fail while your photo is being sent.
- When the face service stops answering on a working connection, LiveCam
  notices in about 12 seconds instead of 30 and reconnects. When nothing
  gets through at the moment you go live, the live status says the internet
  connection is the problem after about ten seconds instead of thirty. When
  the face service cannot be reached while your internet works, it says the
  face service is not answering, instead of reporting no internet
  connection, and retries at a gentler pace.
- When the face service is very busy, LiveCam says so and retries on its own
  at a gentler pace, instead of reporting an unstable connection that sent
  you to check your internet, and it no longer promises how soon your face
  comes back. When every face session available to LiveCam stays in use for
  a few minutes, the call stops trying and says to start it again in a few
  minutes, instead of retrying for the rest of the call.
- When the face service refuses the licence (revoked, paused, expired, not
  activated on this computer, an update required) or face access is
  suspended, LiveCam stops retrying the face and a go-live says why, instead
  of reconnecting in the background forever or asking to restart LiveCam. An
  answer from a company proxy or gateway is no longer mistaken for a licence
  problem. On a network that blocks video calls, LiveCam stops retrying
  after three failed video connections in a row instead of forever; a single
  slow connection, or the service failing for a moment, is not reported as a
  network that blocks video.
- Going live again after stopping, after a start that failed, or after
  switching to another face no longer runs into the face service's pause
  after many reconnections: LiveCam keeps its face session access for a few
  minutes and reuses it, a shaky network no longer spends one on every
  reconnection, and face starts that failed because the face service was
  unavailable no longer count as reconnections. When that pause does come,
  the face waits it out and comes back at its end, instead of asking again
  and again in the meantime.
- During a call, the live status at the top of the window says when the
  voice or the video has stopped, when your face is still connecting or
  coming back, or when the image is paused, on every page and in the same
  words and colour as the dashboard, instead of « En direct » in green while
  part of the call has stopped. A stopped video or voice always reads
  « Vidéo arrêtée » or « Voix arrêtée », whatever stopped it, and the line
  that says why ends with « Relancez le direct. » once the call has ended,
  or with how to bring the video back while the voice goes on.
- The tabs at the top of the window no longer move when a call starts,
  reconnects or changes state: the call's status keeps a fixed place beside
  them, and in a narrow window « Visite guidée » shows as its book icon,
  with its name on hover, so the whole bar fits. While a call starts or
  stops, the dimmed tabs say « Le direct démarre. » or « Le direct
  s'arrête. » instead of asking you to stop the call.
- When a call with only the face or only the voice stops by itself, for
  example because the camera or the microphone was unplugged, LiveCam says
  so at once and names the cause, and the dashboard keeps the explanation
  and what to do until the next call starts. A webcam that stops sending
  pictures without reporting an error now ends the video within a few
  seconds with a message that the camera is not responding, instead of
  showing a frozen picture as live and later blaming the face service.
- When LiveCam's own video processing stops unexpectedly during a call, it
  now says that the video stopped and to start the call again, instead of
  asking you to check your camera's connection. When the video stops
  responding, LiveCam closes it once it has given up on it, so a new call
  starts at once and an update is no longer refused as if a call were still
  on.
- Stopping the video no longer waits behind the transformed face on a slow
  or busy computer: your face leaves the call as soon as you stop. When a
  stop takes longer than expected, the message saying it did not respond
  goes away by itself once the stop completes.
- When the voice stops responding during a call and then does not stop when
  you end the call, LiveCam shows that the stop is still to be confirmed and
  lets you stop again, instead of showing the call as ended while the
  microphone may still be in use.
- Cancelling a go-live that takes too long is now always honoured; in rare
  cases the call could still start a few seconds later. Closing LiveCam
  while a call is starting stops that start at once, so the camera no longer
  turns on as LiveCam exits.
- While no app shows the LiveCam camera or uses LiveCam's voice yet, the
  live status says so calmly and names what to do in the meeting app: turn
  the video on and choose LiveCam Virtual Camera, and choose the microphone
  named exactly as meeting apps list it. It no longer shows red lines that
  only asked to choose the camera or named a "LiveCam" microphone that no
  app shows. When Windows mutes the output LiveCam plays your voice into,
  the warning names that output as Windows lists it and says where to turn
  it back on, instead of pointing at a microphone.
- The « Aperçu » panel no longer shows a frame rate in red during a healthy
  call: that number counted the panel's own refresh, not what the meeting
  receives. The panel now shows only the picture of your call.
- With audio and video sync on, turning the face off and back on during a
  call no longer shows an old transformed picture from before the
  switch-off.
- Sending a support report during a call no longer stops the call's video
  when the video is slow to describe its state; the report notes that part
  as unavailable instead.
- When the computer's date or time is wrong, activation, updates and the
  face service now say to check the clock instead of the internet
  connection.

#### Voices

- Starting the voice, switching voices during a call and changing the voice
  settings no longer wait on a slow or unreliable connection to set the
  automatic pitch: LiveCam uses what it already knows about the voice and
  asks the service only for a voice it cannot answer for, waiting at most
  two seconds.
- A trained voice keeps the speed setting this computer earned, including
  the lowest-latency one, when LiveCam cannot reach its service, instead of
  falling back to a slower one after a day offline. Starting a voice no
  longer waits for the service when a setting is already known: it is
  refreshed in the background once the connection is back.
- Starting a call right after « Tester ma voix » no longer loads the voice
  from scratch: it is prepared again as soon as the test ends, as it already
  was after a call.
- A new voice is now used in your calls as soon as it is ready when no other
  voice is set for them: « Terminé » takes you back and the dashboard names
  it, with no extra click. A voice already used in your calls is never
  replaced by a new one. Looking at a voice that is being created, that
  failed or that waits for your choice no longer stops your calls from using
  your current voice, and leaving Voix while a first voice is being created
  no longer loses it.
- Creating a voice now rides out trouble on the online service. While the
  service is briefly unreachable, a voice being started or a chosen voice
  being sent waits for it to come back, for up to six hours, instead of
  failing after about twenty minutes, and a voice already in creation
  carries on once it is back instead of having to be started again. A
  creation interrupted on our servers starts again instead of waiting for
  hours and then failing, and a trained voice that finishes while the
  service's storage is briefly unavailable is delivered once the storage is
  back, instead of failing and having to be created again. When the service
  stays unreachable beyond six hours, or an interrupted creation cannot
  start again, the voice fails and the creation is not counted.
- When the answer to a new voice, a retry or a full clone is lost on the
  way, because LiveCam's voice service stopped or the online service did not
  answer, the voice finds out what happened instead of failing at once: it
  carries on if the creation had started, or shows it was interrupted if it
  had not. A new voice whose sending was cut off on the service's side shows
  as interrupted within about fifteen minutes, instead of staying in
  progress for hours and holding a place among the day's voices.
- A voice whose training stopped partway through is no longer delivered as
  if it were complete. Its creation fails without being counted, so it can
  be created again.
- When the follow-up of a voice in creation is interrupted, the message
  names the real cause (the service not answering, the licence on this
  computer, the clock, a security program) instead of always blaming the
  internet connection.
- Retrying a voice whose long recording failed to upload on an unstable
  connection now starts right away, instead of each failed try holding an
  upload slot for up to three hours. When too many voice uploads are in
  progress or were left unfinished, the message suggests restarting a voice
  whose upload failed, or trying again in a few hours.
- Cancelling a new voice while its recording is still being sent now stops
  the sending at once, instead of sending to the end, which could take a
  long time on a slow connection and held back an update. The recording
  stays with the voice, so trying again does not ask for it.
- Cancelling the full clone of an instant voice just as it starts no longer
  lets it start, or count, anyway, and a cancel at the moment its
  installation starts no longer removes the voice: a cancel in time keeps
  the instant voice as it was, and a later one lets the full clone finish
  and says so. An instant voice moving to the full clone now says it stays
  usable, on Voix and on the dashboard.
- « Annuler l'ajout ? » now closes by itself once the voice can no longer be
  cancelled, Voix keeps showing the voice while a cancel is answered, and a
  cancel that comes too late says the voice is kept.
- When a recording added for a fully cloned voice cannot be read, LiveCam
  says so and makes the voice from the others, or lets you choose other
  recordings. When none of them can be read, it says at once that the audio
  format could not be read, instead of starting a creation that could not
  succeed. An audio file chosen for a new voice that can no longer be read
  (moved, deleted, or on a drive that was removed) is reported as such,
  instead of as a connection problem, and no voice is added.
- The warning that a recording shorter than five minutes seems to hold more
  than one person talking, announced in 0.10.0, now appears when a voice is
  fully cloned from it. During the full clone of an instant voice, it offers
  to cancel the full clone and keep your voice as it is; once that full
  clone is made, it only lets you know.
- When a voice is made from a long recording and the quality checks on what
  the voice learns from cannot run, the creation stops with a message asking
  to try again in a few minutes, instead of finishing without those checks.
- Installing a voice on an unstable connection picks up where it stopped,
  within a try, on the next try, when you retry it yourself and after
  LiveCam restarts, instead of starting over, and an expired download link
  is renewed on its own. The install keeps going as long as each try gets
  further, and stops only after five tries in a row that make no headway;
  tries that LiveCam's voice service did not answer, for example while it
  restarted, no longer count. When one file of a voice fails, the install
  says so at once.
- Deleting a voice whose installation failed also removes the files it had
  already downloaded, its sample included, instead of leaving them behind
  for up to a week. Choosing a voice whose files are gone from this computer
  now really downloads them again, as the message says, and a voice that
  cannot be downloaded again says so.
- The download that enables instant voices keeps its progress on slow or
  unstable connections: a dropped connection or an expired download link
  costs only the last few seconds instead of up to several hundred
  megabytes, the rest carries on while one part retries, and a restart
  resumes where it stopped. A security program briefly holding the file at
  the very end no longer fails it, and trying again after a longer hold
  finishes without downloading it again. When the daily download limit is
  reached, the download stops and says to try again tomorrow, instead of
  showing a frozen download.
- The instant voice download stays in view once its window is closed: where
  you add a voice, Voix shows how far it is or why it failed, and a short
  message says when instant voices are ready. Stopping it with
  « Interrompre » no longer reads as a failure, and it now stays stopped
  after a restart until you click « Télécharger » again, keeping what was
  downloaded; a download cut short by a crash or by closing LiveCam still
  carries on at the next start. After an update replaces this download,
  LiveCam frees the space the previous version took, about 2.5 GB, at its
  next start once the new one is fully installed; the previous version stays
  until then. When an update changes this download while an earlier version
  was only partly downloaded, the space that unfinished download took, up to
  about 2.5 GB, is freed at the next start.
- On a computer whose graphics card or driver cannot run a voice live, Voix
  says so and why before you look for a recording, the add button is dimmed,
  and neither way of cloning appears chosen. Voices made earlier no longer
  look ready: each says it is not available on this computer and why,
  « Tester ma voix » is unavailable, no voice is marked as used for calls,
  and the dashboard's voice switch is off with the same reason, so calls
  start with the face alone. Your voice choice is kept for when the computer
  can run it again. Retrying a failed voice and moving an instant voice to
  the full clone are unavailable there too, so no clone is spent on a voice
  this computer cannot use.
- When the first check of this computer's graphics card does not answer in
  time, LiveCam asks once more, so a computer that cannot run a voice says
  so on the dashboard and on Voix instead of letting you try first. A check
  that could not run no longer hides an answer LiveCam already had.
- The voice panel no longer moves while you use it: starting or stopping
  « Tester ma voix » no longer adds or removes lines (the locked voices and
  devices say why when you point at them), and the rename and delete buttons
  keep their places when a voice finishes (delete is dimmed, with its
  reason, while a voice is being created). Coming back to a voice in
  training no longer shows « L'apprentissage commence » whatever the
  progress, and an instant voice no longer has an « Instantané » label
  beside its name: the line under the name already says so.
- On Voix, a voice's sample that cannot be loaded no longer flickers:
  LiveCam tries again after a short wait that grows each time, and a voice
  whose files are damaged says its sample is not available. After browsing
  many voices, coming back to one no longer shows a play button that does
  nothing.
- Pressing play on a recording or a voice sample no longer freezes the
  window while the sound gets ready, for example while a recording is still
  downloading from a cloud folder: the play button shows a spinner until the
  sound starts, and pressing it again cancels.
- The window no longer stutters or freezes for a moment when you pause or
  watch a recording play while the sound device stops responding, when you
  open Visage or switch to another face, or when a message appears while the
  disk is busy. The picture of a long recording appears in a moment instead
  of after several seconds; for recordings longer than about twelve minutes,
  it is drawn from samples of the whole recording.
- Opening the microphone check and closing it without finishing no longer
  marks a checked microphone « À vérifier »: a microphone loses its check
  only when the check hears nothing from it or cannot open it.
- « Configurer le son » on Voix and « Vérifier » in « Avant de passer en
  direct » now open the output step directly when the microphone is already
  checked, and the line above « Configurer le son » says whether the
  microphone or the output of your calls is the one to set up. The guided
  start's last step and the voice setup's last step name the same
  microphone, and the guided start asks you to check your microphone and
  output first when they are not checked yet.
- When the virtual microphone is not installed, LiveCam always says so, even
  if another device's name contains "Virtual", and the « Installer » button
  of « Où envoyer votre voix » opens the installation. In « Où vous
  entendre », the headphones and speakers list says it is searching while it
  is read again, and says when no output is found.

#### Faces and looks

- A portrait taken with a phone now shows the right way up everywhere in
  LiveCam: when you add it, in the face library and during calls. If a face
  added earlier still shows sideways, add its photo again.
- The photos you add for a face, an outfit, a hairstyle or a décor no longer
  keep the hidden details that cameras and photo apps store in them (where
  and when the photo was taken, on which device, comments): LiveCam removes
  them before a photo is kept or sent anywhere, and cleans the photos you
  added before at its next start. If it cannot read one of them in full or
  cannot change it, that face may show sideways, or be refused when a call
  starts, until you add the photo again.
- A photo whose file name says another format than the one it holds (for
  example a WebP picture saved as .jpg) now shows on Visage, where the
  face's picture and its outfit, hairstyle or décor photos stayed empty
  although the call used the photo. Faces already added this way show again
  too. A photo file cut short by an interrupted download or copy is refused
  when you add it, instead of becoming a face whose missing part was made
  up.
- While a new face's photo, a look or a décor is being prepared, the rest of
  LiveCam stays usable, including the dashboard to stop a call. The photo
  wait closes with « Fermer » or Escape and the preparation carries on:
  Visage shows how it is going, and the choice between your photo and the
  prepared one, or the reason it failed, waits there. A look or décor being
  prepared, and the message when it could not be, are still there after a
  visit to another page. An update waits for a photo preparation in
  progress.
- « Terminé » no longer leaves silently when a prepared look or décor has
  not been used yet: it asks whether to use it first, so the call does not
  keep the old one by mistake.
- On a slow or unstable connection, asking again for a photo preparation, a
  look or a décor that did not come back now returns the one already made
  instead of making it again, also after picking the same photo again or
  after trying something else that did not arrive either. A finished photo
  preparation is kept about ten minutes for this, and asking again for it no
  longer counts toward the per-minute limit.
- When a look, a décor or a portrait is refused because what was sent is too
  large, LiveCam says the file is too heavy and asks for a lighter one,
  instead of pointing at the connection.
- Renaming or deleting a face while its look or décor is being applied is
  now kept: the face no longer goes back to its old name, and a deleted face
  no longer comes back without its photo. After you use a new look, the
  other faces in your library keep their pictures instead of briefly showing
  their initials, and the face whose look changed goes straight from its old
  picture to its new one.
- Saving a new face no longer depends on the video starting: a face whose
  photo was already checked is saved even when the video cannot start at
  that moment, and during a call the call's face changes only once the new
  face is saved. When a new face cannot be saved, « Nommez ce visage » comes
  back with your photo and its name, so you can save it again without
  preparing the photo again. Choosing a face whose photo cannot be read for
  a moment no longer says the photo is missing or asks you to delete the
  face.
- When your library cannot be loaded, Visage keeps its message and
  « Réessayer » instead of offering to add a first face that could not be
  saved. Escape on « Nommez ce visage » goes back to the photo choice with
  the prepared photo still there; « Annuler » still abandons the new face.
  The dashboard's face switch says why it is unavailable before a face is
  chosen, without the hand pointer, and the card of a face being prepared no
  longer promises how long it takes.
- When the shared system component LiveCam updates during installation has
  not finished updating, adding a face or going live with one now says to
  restart the computer, then to reinstall LiveCam if the problem persists,
  instead of only asking for a reinstall. The installer offers to restart
  the computer when that update needs it, and says so at the end of the
  installation when that update failed, instead of looking complete while
  faces could not be used.

#### Installation, updates and licence

- On computers where an antivirus, a VPN or a company network checks secure
  connections, licence activation, installation, updates, face photos, voice
  creation and downloads, and support reports work again: LiveCam trusts the
  same certificates as Windows and your browser, and a slow certificate
  check no longer reads as "no connection". When such a program or the
  network does block LiveCam's secure connection, activation, installation,
  update checks, face photos, the live face, voice creation and voice
  downloads now say so and suggest another network or allowing LiveCam in
  that program, instead of asking you to check the internet connection.
- Proxy or certificate settings that other programs left on the computer no
  longer stop voice creation and downloads, and a proxy set in the
  computer's environment variables no longer stops LiveCam from reaching its
  own local service.
- Downloading LiveCam's engine or an app update on a connection that keeps
  dropping now keeps going as long as each reconnection brings more of the
  file, instead of stopping after twelve reconnections. On a connection too
  slow to ever finish, it stops with a message after about ten minutes
  instead of trying for hours, and keeps what was downloaded, so trying
  again picks up where it stopped. Installing or updating the engine checks
  the download once instead of twice, so it finishes a few seconds sooner,
  and more on a slow disk.
- During a call, « Mettre à jour » now waits and says why, instead of
  failing after the click. An update that finishes downloading during a call
  no longer ends in an error: it waits until the call ends, Paramètres says
  why, and « Mettre à jour » then installs it without downloading it again.
  An update that finishes while you test your voice now installs, instead of
  stopping without a word and offering « Mettre à jour » again.
- While an update downloads, the dashboard shows its progress, as Paramètres
  does, instead of still offering to install it. A failed update check in
  Paramètres is said once, under the card, instead of also in a
  notification, and the update progress bar keeps one length when its text
  changes.
- During a call, « Désactiver sur cet appareil… » now waits for the call to
  end and says why, like « Mettre à jour » next to it, instead of ending the
  call and the voice without warning; it also waits while a voice recording
  is being sent. After deactivating, LiveCam confirms that the licence was
  deactivated.
- When a licence has ended, been revoked or been suspended, LiveCam says
  what to do next wherever the licence stops something, such as the voice
  download or the video: ask the person who provided LiveCam to renew it or
  for a new key, then enter the key. A licence that ends in the next two
  weeks says how to renew it, in Paramètres and on the dashboard, whose
  notice no longer has a « Gérer » button that only led to the same
  information. The licence screen asks for the licence key received with
  LiveCam, instead of a key provided by an administrator.
- The licence's end date and countdown follow your computer's calendar: just
  after midnight on its last day, a licence reads « Expire aujourd'hui »
  instead of « Expire demain », and a licence that ends in the early hours
  shows that day's date. A date on the first of a month reads « 1er », as
  elsewhere in the app.
- The virtual camera and microphone setup window closes by itself, with a
  confirmation, once both are installed. Its buttons are « Plus tard » and
  « Vérifier l'installation », and a greyed-out status that looked like a
  button is gone.
- When LiveCam cannot find its data folder at start, it says so and closes,
  instead of opening on a screen whose buttons could not work. On a computer
  short of memory, LiveCam no longer closes right after opening; if it
  cannot set up how a second launch brings its window to the front, a second
  launch simply ends without showing the window.

#### Settings, messages and the window

- When the voice service stops and cannot start again, the bar at the top of
  the window says why and what to do (for example, free up disk space),
  instead of repeating the same line after every « Redémarrer ». While the
  voice service restarts, or repairs its files first, the bar says so and
  hides « Redémarrer », so a second press no longer cancels the restart in
  progress and starts it over.
- Messages that suggest contacting support simply say « contactez le
  support », without pointing to an order or an administrator, and the
  warning about voices or faces that could not be read is one short
  sentence.
- An error notification now leaves when you try the same thing again: a
  refused photo no longer stays on screen while the next one is checked and
  prepared, and a failed go-live no longer stays over « Vous êtes en
  direct » once the next one starts. A second error about the same action
  replaces the first instead of stacking under it, and deleting a face or a
  voice removes the errors about it. The messages for a face that could not
  be deleted and for a voice choice that did not go through say to try
  again.
- Notifications appear just below the top bar, so « Tableau de bord »,
  « Visage », « Voix » and « Paramètres » answer the first click even while
  an error notification waits to be closed, and they stay below the banner
  that reports an app-wide problem. A notification that is closing no longer
  catches the next click, and stacked notifications show only their edges
  behind the front one, without a stray word of their text.
- During a call, « Réactivité maximale » and « Voix nette en parlant vite »
  say that they apply to the next call. Aide's technical information names
  the voice service on this computer, « Service de voix », instead of
  « Connexion au service », which said « Connecté » even without an internet
  connection. Settings are now saved while a security program or a search
  indexer is reading the settings file, instead of failing with a message
  that they could not be saved.
- Every dialog now works from the keyboard: it takes the keyboard as it
  opens and keeps it after you click one of its buttons, Tab stays inside
  it, Escape closes it the way its « Annuler » or close button does (never
  its confirmation), and closing it brings you back where you were. Closing
  the window during a call and pressing Escape keeps the call going. The
  guided tours close with Escape.
- Rename dialogs open with the name selected, ready to type over, and Enter
  renames a voice as it already renamed a face. The licence key field is
  ready to type in when the activation screen opens. Moving through the app
  with Tab now shows where you are on the switches and on the « Tableau de
  bord », « Visage » and « Voix » tabs, as on the buttons. Screen readers
  announce the state of each device on Voix (« Vérifié », « À vérifier »,
  « À choisir », « Absent ») and when a change to your look or décor is
  waiting to be applied.
- A name longer than 40 characters is no longer saved cut short without a
  word: the counter shows the real length, and the name is saved only once
  it fits, for voices and faces alike.
- The guided tour no longer opens on a step that promised a preview of your
  call on a card that has none. It has four steps, and the last one says
  where to check the picture the people in your call see: « Aperçu », next
  to the stop button while you are live. Opened during a call, its last step
  says you are live, which camera to pick in your meeting app, and to click
  « Arrêter le direct » once you are done, instead of telling you to start
  the call.
- Switches that are off are easy to see in both the light and the dark
  theme. A window too small for a dialog no longer cuts it off: the dialog
  stays inside the window with its buttons in view and its content
  scrolling. In a small window, the first-run screen scrolls instead of
  sliding under the title bar or hiding « Envoyer un rapport », and after
  maximizing, restoring or snapping the window, the dashboard rearranges
  itself right away.
- The side panels of Visage and Voix share exactly the same layout, and
  their cards, the buttons inside them and the face and voice pictures react
  when the pointer is over them. Buttons and labels shown over a picture
  stay readable on light and dark photos, and the dot in front of a status
  message sits at its middle when it takes two lines. The camera list's
  refresh button says « Actualiser », as on Voix, and the "more below" arrow
  sits beside the live button instead of over that refresh button in narrow
  windows.
- With Windows animation effects turned off, the waiting signs show a still
  loading ring and a still bar, instead of a tiny dot and an empty bar that
  looked stuck. A change to that setting is picked up the next time you come
  back to LiveCam.

---

The installer above is the only file to download; the source archives are GitHub's automatic copy of this note.
