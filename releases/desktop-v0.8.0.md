# LiveCam 0.8.0

Released 2026-09-13.

This release focuses on trained voices in live sessions and on creating a
voice from a short recording.

### Added

- “Parole rapide plus nette” in advanced voice settings preserves more of
  fast speech by allowing a little more delay. It is off by default and
  takes effect at the next session start.

### Changed

- The microphone check measures your speaking voice locally and waits for
  a stable result. It asks you to continue reading when it needs more speech.
  The measurement stays tied to the microphone used for the check.
- Voice creation gives clearer guidance: start with 15 to 30 seconds of
  clear speech from one person.
- Removed the “Votre voix reste la vôtre” dialog from voice creation.
- Notifications appear at the top center of the window, including over
  navigation when necessary.

### Fixed

- Live voice raises quiet speech before conversion. The microphone check
  asks for a stronger signal when the input remains too quiet to use.
- Automatic voice adjustment reports when the microphone's measurement is
  unavailable instead of silently reusing a measurement from another device.
- Voice creation checks both resemblance and speech clarity across two
  speaking ranges using the settings live sessions actually apply.
- Short recordings of a single speaker can pass the clarity check without
  requiring an eight-second uninterrupted passage.
- Recordings between 30 and 49 seconds can contribute a second reference
  when at least ten usable seconds remain after the first reference.
- Reference preparation keeps complete words at the end of a recording
  instead of discarding an unfinished sentence in full.
- Reference preparation keeps speech after long pauses and checks the
  recording through its final sample.
- Voice creation filters generated speech that strays too far from the
  reference voice. Results can still vary between creations.
- A reference that repeatedly prevents stable speech generation now ends
  with guidance to try another recording instead of waiting for the full
  training timeout.
- Voice creation reports a generation failure accurately when the remaining
  work is stopped, instead of presenting it as a cancellation.

---

The installer above is the only file to download; the source archives are GitHub's automatic copy of this note.
