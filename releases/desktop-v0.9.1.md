# LiveCam 0.9.1

Released 2026-09-21.

The 0.9.0 installer could not finish on any computer. This release ships the
same LiveCam with a working installer.

### Fixed

- Installing or updating LiveCam stopped with the message that LiveCam was
  still open, even on a computer where it had never run. The installer had
  locked the files it prepared so tightly that it could no longer move them
  into place. The prepared files now keep the same permissions as the
  installation folder, and the update completes.

---

The installer above is the only file to download; the source archives are GitHub's automatic copy of this note.
