# LiveCam 0.8.1

Released 2026-09-14.

Small corrections to voice creation found while reviewing the 0.8.0 release.

### Fixed

- A very short recording whose only clean stretch is a few seconds is
  declined with guidance instead of being sent to voice creation with too
  little speech.
- When a recording between 30 and 49 seconds keeps its best passage at the
  end, that passage stays the main reference and the shorter opening part
  is the secondary one.
- Voice creation no longer writes temporary download links into its
  processing logs.

---

The installer above is the only file to download; the source archives are GitHub's automatic copy of this note.
