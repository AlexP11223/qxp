---
title: '[GSoC] QuarkXPress import, project results'
---

libqxp currently supports importing of Windows and Mac 3.3-4.0 documents.
Import of text and shapes is almost complete, but it lacks pictures because reverse engineering of other parts of the format took more time than expected and picture format seems to be quite complicated too.

Supported features:

- Pages, facing pages.
- Boxes (rectangles, ovals, Bezier).
- Lines, Bezier curves.
- Text paths.
- Object groups.
- Rotation.
- Text, including linked text boxes/paths.
- Font, size, alignment, leading, H&J, bold/italic/underline/outline/shadow/strike/subscript/superscript/caps.
- Colors (including shades), gradient (only linear, radial, rectangular).
- Line/frame color, width, line caps and corners, arrows, dashes.

Missing features:
- Pictures.
- Lists.
- Columns. Not supported by librevenge (drawing interface)/LO Draw.
- Non-rectangular box corners.
- Custom text area shapes (for ovals, Bezier text paths, ...). Not supported in librevenge/ODF.
- Complex dash patterns (more than 2 different dashes) and stripes. Not supported in librevenge/ODF.
- Paragraph leading is not perfect in some cases because ODF fo:line-height works a bit differently.
- Some advanced H&J and formatting properties that are not supported (or partially supported) by ODF or LO Draw.
- Mid-linear, diamond gradients. Not supported in librevenge/ODF.
- Skewing.

Code:

libqxp
[https://gerrit.libreoffice.org/gitweb?p=libqxp.git&a=search&h=HEAD&st=author&s=alex](https://gerrit.libreoffice.org/gitweb?p=libqxp.git&a=search&h=HEAD&st=author&s=alex)

libqxp-test
[https://gerrit.libreoffice.org/gitweb?p=libqxp-test.git&a=search&h=HEAD&st=author&s=alex](https://gerrit.libreoffice.org/gitweb?p=libqxp-test.git&a=search&h=HEAD&st=author&s=alex)

OleToy, reverse engineering of qxp3.3-4.0
[https://github.com/renyxa/re-lab/commits/master?author=alex.pantec@gmail.com](https://github.com/renyxa/re-lab/commits/master?author=alex.pantec@gmail.com)
