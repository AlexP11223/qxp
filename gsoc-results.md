---
title: '[GSoC] QuarkXPress import, project results'
---

libqxp currently can import documents and templates created by QuarkXPress 3.1-4.1 for Windows and Mac.
Import of text and shapes is almost complete, but it lacks pictures because reverse engineering of other parts of the format took more time than expected and picture format seems to be quite complicated too.

Supported features:

- Pages, facing pages.
- Boxes (rectangles, ovals, Bezier).
- Lines, Bezier curves.
- Text paths.
- Object groups.
- Rotation.
- Text, including linked text boxes/paths.
- Font, size, alignment, paragraph rules, leading, H&J, tabs, bold/italic/underline/outline/shadow/strike/subscript/superscript/caps.
- Colors (including shades), gradients (only linear, radial, rectangular).
- Line/frame color, width, line caps and corners, arrows, dashes.

Missing features:

- Pictures.
- Non-English texts. Need sample docs to determine language values and encodings.
- Columns. Not supported in librevenge (drawing interface)/LO Draw.
- Non-rectangular box corners.
- Custom text area shapes (for ovals, Bezier text paths, ...). Not supported in librevenge/ODF.
- Complex dash patterns (more than 2 different dashes) and stripes. Not supported in librevenge/ODF.
- Paragraph leading is not perfect in some cases because ODF fo:line-height works a bit differently.
- Paragraph rule margins. Not supported in librevenge/ODF.
- Custom kerning, tracking, hyphenation exception. Not supported in librevenge/ODF.
- Auxiliary dictionary. Not supported in librevenge/ODF.
- Some advanced H&J and formatting properties that are not supported (or partially supported) by ODF or LO Draw.
- Mid-linear, diamond gradients. Not supported in librevenge/ODF.
- Skewing.

Code:

libqxp
[https://gerrit.libreoffice.org/gitweb?p=libqxp.git&a=search&h=HEAD&st=author&s=alex](https://gerrit.libreoffice.org/gitweb?p=libqxp.git&a=search&h=HEAD&st=author&s=alex)

libqxp-test
[https://gerrit.libreoffice.org/gitweb?p=libqxp-test.git&a=search&h=HEAD&st=author&s=alex](https://gerrit.libreoffice.org/gitweb?p=libqxp-test.git&a=search&h=HEAD&st=author&s=alex)

libqxp integration to LibreOffice
[https://gerrit.libreoffice.org/gitweb?p=core.git;a=commitdiff;h=e59b5b1fc7266d56a17e387b8df0f6d6956e8ea5](https://gerrit.libreoffice.org/gitweb?p=core.git;a=commitdiff;h=e59b5b1fc7266d56a17e387b8df0f6d6956e8ea5)

OleToy, reverse engineering of qxp3.3-4.0
[https://github.com/renyxa/re-lab/commits/master?author=alex.pantec@gmail.com](https://github.com/renyxa/re-lab/commits/master?author=alex.pantec@gmail.com)
