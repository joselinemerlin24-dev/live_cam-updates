# LiveCam 0.10.2

Released 2026-09-28.

Clearer messages when something needs you, a way to cancel a slow start of
a call, and corrections found by using LiveCam during real calls.

### Added

- When LiveCam cannot start its local service, the error screen now offers
  "Envoyer un rapport", and the report button in Paramètres keeps working
  while the service is stopped. If the report cannot be sent, LiveCam offers
  to save it as a file.
- A go-live that is still starting after about 30 seconds now offers
  "Annuler". It stops whatever had already started and brings you back to
  the dashboard, ready to go live again. If you do not cancel, a slow first
  voice start still gets all the time it needs.

### Changed

- Error messages that ask you to do something now stay on screen until you
  close them. Information and confirmations still close by themselves, and
  the same error shown twice appears only once.
- The "Synchronisation complète" option moved from the home page's start
  panel to Paramètres, under "Paramètres avancés", so the panel fits the
  window with both the face and the voice on. During a call with the option
  on, the panel still shows whether image and voice are aligned.

### Fixed

- While the local service is stopped, "Démarrer le direct" and the other
  actions that need it now say so every time they are clicked and point to
  "Redémarrer", instead of doing nothing. The note that locks the devices on
  the Voix page now names what to stop.
- On a network that blocks video calls, as in some offices and hotels, a
  face go-live that cannot connect now says the network may be the cause
  and suggests trying another one, instead of asking you to restart LiveCam.
- When the microphone disappears during a call, the app now shows within a
  few seconds that the voice stopped, and why, instead of about half a
  minute later.
- The app now notices right away when the voice stops, recovers after a
  device change, finishes preparing, or finishes installing, instead of up
  to 15 seconds later.
- The "Votre ordinateur est très occupé" notice now appears at the top of
  the Tableau de bord, where you see it before a call. It no longer appears
  after the first voice preparation following a restart, an update or a new
  installation, which is always slower even on an idle computer.
- After a call, the "Votre ordinateur est très occupé" notice now reflects
  how the computer is doing after the call, not before it.
- Clicking "Aperçu" during a call no longer also opens the Voix page.
- Deleting the selected voice no longer shows a "voice still busy" warning
  after the delete succeeded, and a voice that is ready is no longer asked
  to be prepared again every half second.
- In the microphone dialog, the "no sound from the microphone" warning no
  longer makes the dialog jump, so a click in the list picks the microphone
  you aimed at.
- The voice rename dialog now says "voix", like the rest of the Voix page.

---

The installer above is the only file to download; the source archives are GitHub's automatic copy of this note.
