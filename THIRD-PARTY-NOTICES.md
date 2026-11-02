# PORDA macOS conversion components

Filee 2.2.0 is bundled as a local command-line runtime, without installing its GUI. Its license and the dependencies' notices are included inside PORDA.app under Contents/Resources/backend/tools/filee. Third-party components retain their original licenses; PORDA's project license does not replace them.

- Filee source and release: https://github.com/KnifeLemon/Filee/releases/tag/v2.2.0
- 7-Zip binary and corresponding source: https://github.com/ip7z/7zip/releases/tag/26.05
- 7-Zip 26.05 replaces Filee's bundled macOS-26-only binary. The official arm64 code is used and locally ad-hoc signed; no deployment-version patch was applied.

## Filee license

MIT License

Copyright (c) 2026 Myeonggu Kim (KnifeLemon) and Filee contributors

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


## Filee dependency notices

# Third-party notices

Filee is MIT-licensed. It uses and redistributes the following third-party software.
Each component remains under its own license.

## Libraries (NuGet)

| Component | License | Project |
|---|---|---|
| Avalonia UI | MIT | https://github.com/AvaloniaUI/Avalonia |
| NWayland (used by Avalonia.Wayland) | MIT | https://github.com/kekekeks/NWayland |
| CommunityToolkit.Mvvm | MIT | https://github.com/CommunityToolkit/dotnet |
| SharpHook (libuiohook) | MIT (libuiohook: GPL-3.0 with linking exception / LGPL-3.0) | https://github.com/TolikPylypchuk/SharpHook |
| Magick.NET / ImageMagick | Apache-2.0 / ImageMagick License | https://github.com/dlemstra/Magick.NET |
| ImageMagick delegate libraries (libheif, libde265, libwebp, libjpeg-turbo, libpng, libtiff, zlib, …) | Various (LGPL-2.1+, BSD, zlib) | bundled inside Magick.NET |
| PDFsharp | MIT | https://github.com/empira/PDFsharp |
| PDFtoImage | MIT | https://github.com/sungaila/PDFtoImage |
| PDFium (bblanchon.PDFium) | BSD-3-Clause / Apache-2.0 | https://pdfium.googlesource.com/pdfium |
| SkiaSharp | MIT | https://github.com/mono/SkiaSharp |
| Svg.Skia (incl. Svg, ShimSkiaSharp, ExCSS; text shaping in `Filee.Engines/Vector/OutlinedTextPlayback.cs` adapted from it) | MIT | https://github.com/wieslawsoltes/Svg.Skia |
| HarfBuzzSharp | MIT | https://github.com/mono/SkiaSharp |
| SharpCompress (zstd decompression for engine downloads; RAR, 7z and TAR comics) | MIT | https://github.com/adamhathcock/sharpcompress |
| Unhwp | MIT | https://github.com/iyulab/unhwp |
| Markdig | BSD-2-Clause | https://github.com/xoofx/markdig |
| ExcelNumberFormat | MIT | https://github.com/andersnm/ExcelNumberFormat |
| ExcelDataReader | MIT | https://github.com/ExcelDataReader/ExcelDataReader |
| PdfPig (PDF text, layout and pictures) | Apache-2.0 | https://github.com/UglyToad/PdfPig |
| MimeKitLite (e-mail / MIME parsing) | MIT | https://github.com/jstedfast/MimeKit |
| MsgReader (Outlook .msg reading) | MIT, Copyright (c) Kees van Spelde | https://github.com/Sicos1977/MSGReader |
| OpenMcdf (OLE compound files, used by MsgReader) | MPL-2.0 (source: the project page) | https://github.com/openmcdf/openmcdf |
| RtfPipe (RTF → HTML, used by MsgReader) | MIT, Copyright (c) 2018 Eric Domke | https://github.com/erdomke/RtfPipe |
| UTF.Unknown (charset detection, used by MsgReader) | MPL-1.1 (source: the project page) | https://github.com/CharsetDetector/UTF-unknown |
| Microsoft.Maui.Graphics, Microsoft.IO.RecyclableMemoryStream (used by MsgReader) | MIT | https://github.com/dotnet/maui, https://github.com/microsoft/Microsoft.IO.RecyclableMemoryStream |
| YamlDotNet (YAML reading and writing) | MIT, Copyright (c) Antoine Aubry and contributors | https://github.com/aaubry/YamlDotNet |
| Tomlyn (TOML reading) | BSD-2-Clause, Copyright (c) Alexandre Mutel | https://github.com/xoofx/Tomlyn |
| ACadSharp (DWG/DXF reading and writing; includes CSMath and CSUtilities) | MIT, Copyright (c) Albert Domenech | https://github.com/DomCR/ACadSharp |
| SharpGLTF.Core (glTF / GLB reading and writing) | MIT, Copyright (c) Vicente Penades | https://github.com/vpenades/SharpGLTF |
| AngleSharp | MIT | https://github.com/AngleSharp/AngleSharp |
| pypandoc-hwpx (Pandoc AST mapping and package layout in `Filee.Engines/Hwp/Hwpx`, incl. the `blank.hwpx` reference document) | MIT, Copyright (c) 2024 pypandoc-hwpx Contributors | https://github.com/msjang/pypandoc-hwpx |
| Microsoft.Extensions.* | MIT | https://github.com/dotnet/runtime |
| cu2qu (fontTools): the cubic-to-quadratic approach followed by `Filee.Engines/Fonts/Cff/CubicToQuadratic.cs` | Apache-2.0, Copyright 2016 Google Inc. | https://github.com/fonttools/fonttools |

libuiohook (the native input hook inside SharpHook) is the fork https://github.com/TolikPylypchuk/libuiohook, licensed
under the GNU LGPL-3.0 (`COPYING.LESSER.md` in its repository). Filee loads SharpHook's unmodified build of it
dynamically; you may replace those libraries with your own build of libuiohook.

Used by the tests only (not redistributed): DocumentFormat.OpenXml (Open XML SDK, MIT, https://github.com/dotnet/Open-XML-SDK) validates the DOCX files Filee writes.

## Engines

Bundled with the installer:

| Component | License | Project |
|---|---|---|
| rhwp | MIT | https://github.com/edwardkim/rhwp |
| 7-Zip (console: `7z.exe`, `7z.dll`) | GNU LGPL-2.1-or-later; parts of `7z.dll`: LGPL with the unRAR license restriction, BSD-3-Clause, BSD-2-Clause | https://www.7-zip.org |
| Microsoft Visual C++ Redistributable (Windows: next to `Filee.exe` and `rhwp.exe`, conda-forge `vc14_runtime`) | Microsoft Visual C++ Redistributable license | https://github.com/conda-forge/vc-feedstock |

The Linux packages contain an rhwp built by Filee's CI from the unmodified source of the same release (tag `v0.8.7`,
commit `1a76570e833917d15817415a53c09ad61ab3203f`, `cargo build --release --locked --bin rhwp` on Ubuntu 22.04), so it
runs on older Linux systems than rhwp's own Linux build. It is under the same MIT license; its `LICENSE` is next to it
(`engines/rhwp`). Windows and macOS use rhwp's release builds.

7-Zip is Copyright (C) 1999-2026 Igor Pavlov; its `License.txt` is installed next to it (`engines/7zip`). The RAR
decompression code in `7z.dll` is under the unRAR license restriction: it may be used to unpack RAR archives, but not
to develop a RAR (WinRAR) compatible archiver or to re-create the RAR compression algorithm. Filee only reads RAR
files. Source code: https://github.com/ip7z/7zip.

Downloaded from their official release pages when the user chooses to install them
(pinned in `src/Filee.Engines/Infrastructure/engines.json`):

| Component | License | Project |
|---|---|---|
| LibreOffice | MPL-2.0 | https://www.libreoffice.org |
| H2Orestart (HWP/HWPX import for LibreOffice) | GPL-3.0 | https://github.com/ebandal/H2Orestart |
| Eclipse Temurin JRE (for H2Orestart) | GPL-2.0 with Classpath Exception | https://adoptium.net |
| Pandoc | GPL-2.0-or-later | https://github.com/jgm/pandoc |
| Ghostscript (conda-forge build) | AGPL-3.0 | https://www.ghostscript.com, https://github.com/conda-forge/ghostscript-feedstock |
| Microsoft Visual C++ Redistributable (for Ghostscript, conda-forge `vc14_runtime`) | Microsoft Visual C++ Redistributable license | https://github.com/conda-forge/vc-feedstock |
| FFmpeg 9.0.2 (gyan.dev "full_build-shared" Windows build; ffmpeg.exe, ffprobe.exe and their libraries, incl. x264, x265, libvpx, LAME, Opus, Vorbis, Theora, OpenCORE AMR) | GPL-3.0-or-later (the build is configured with `--enable-gpl --enable-version3`); FFmpeg itself LGPL-2.1-or-later | https://ffmpeg.org, build: https://www.gyan.dev/ffmpeg/builds/ (source: https://github.com/GyanD/codexffmpeg) |
| calibre (ebook-convert) | GPL-3.0 | https://calibre-ebook.com |
| Tesseract OCR 5.4 (UB Mannheim Windows build, with Leptonica and the MinGW libraries it ships; their notices are in its `doc` folder) | Apache-2.0 (Tesseract); Leptonica BSD-2-Clause; others as listed in the build | https://github.com/tesseract-ocr/tesseract, build: https://github.com/UB-Mannheim/tesseract |
| Tesseract language data (tessdata_fast 4.1.0), downloaded per language when used | Apache-2.0 | https://github.com/tesseract-ocr/tessdata_fast |

These programs run as separate processes. Their source code is available from the linked projects.

## Windows 11 Explorer menu (FileeExplorerMenu.dll)

The DLL is Filee's own C code, compiled with the Zig toolchain (a build tool, not shipped) against the mingw-w64
Windows headers, without a C runtime. Pieces of these projects that can end up in the binary:

| Component | License | Project |
|---|---|---|
| Zig compiler_rt (compiler support routines) | MIT | https://github.com/ziglang/zig |
| mingw-w64 Windows headers and import library definitions | Public domain / ZPL-2.1 | https://www.mingw-w64.org |

## Installer

`Filee-<version>-win-Setup.exe` is Filee's own installer (`src/Filee.Setup`, MIT like the app). It contains the
.NET runtime, Avalonia, SkiaSharp, HarfBuzzSharp, CommunityToolkit.Mvvm and SharpCompress (LZMA) listed in this file,
the x86 branch filter of the LZMA SDK (public domain, Igor Pavlov, https://www.7-zip.org/sdk.html), and the published
app as its payload. Filee 1.x's installer was built with Inno Setup, which is no longer used.

## Fonts and icons

| Component | License | Project |
|---|---|---|
| Noto Sans, Noto Sans Arabic, Noto Sans JP, Noto Sans KR, Noto Sans SC, Noto Sans Devanagari, Noto Sans Thai | SIL Open Font License 1.1 | https://github.com/notofonts |
| Test fonts in `tests/Filee.Engines.Tests/Fonts` (subsets of Noto Sans and Noto Sans KR; not shipped) | SIL Open Font License 1.1 | see `OFL.txt` in that folder |
| Material Design Icons (Pictogrammers) | Apache-2.0 | https://pictogrammers.com |
| Simple Icons 16.35.0 (GitHub Sponsors, Patreon, Ko-fi and PayPal logos in the Sponsor window) | CC0-1.0 | https://simpleicons.org |

The GitHub Sponsors, Patreon, Ko-fi and PayPal names and logos are trademarks of their owners and are used only to link
to each service.

## Documentation theme examples

The optional JSON recipes in `docs/themes/` adapt palette data from Catppuccin, Nord, Dracula and VS Code's classic
Monokai theme. Their source links, colour adjustments and copyright/license notices are in
[docs/themes/NOTICE.md](docs/themes/NOTICE.md). These are documentation examples, not runtime dependencies.


## Bundled 7-Zip license

  7-Zip for Linux and macOS
  ~~~~~~~~~~~~~~~~~~~~~~~~~
  License for use and distribution
  ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

  7-Zip Copyright (C) 1999-2026 Igor Pavlov.

  The licenses for 7zz and 7zzs files are:

         - The "GNU LGPL" as main license for most of the code
         - The "GNU LGPL" with "unRAR license restriction" for some code
         - The "BSD 3-clause License" for some code
         - The "BSD 2-clause License" for some code

  Redistributions in binary form must reproduce related license information from this file.

  Note:
    You can use 7-Zip on any computer, including a computer in a commercial
    organization. You don't need to register or pay for 7-Zip.


GNU LGPL information
--------------------

    This library is free software; you can redistribute it and/or
    modify it under the terms of the GNU Lesser General Public
    License as published by the Free Software Foundation; either
    version 2.1 of the License, or (at your option) any later version.

    This library is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
    Lesser General Public License for more details.

    You can receive a copy of the GNU Lesser General Public License from
    http://www.gnu.org/




BSD 3-clause License in 7-Zip code
----------------------------------

  The "BSD 3-clause License" is used for the following code in 7z.dll
    1) LZFSE data decompression.
       That code was derived from the code in the "LZFSE compression library" developed by Apple Inc,
       that also uses the "BSD 3-clause License".
    2) ZSTD data decompression.
       that code was developed using original zstd decoder code as reference code.
       The original zstd decoder code was developed by Facebook Inc,
       that also uses the "BSD 3-clause License".

  Copyright (c) 2015-2016, Apple Inc. All rights reserved.
  Copyright (c) Facebook, Inc. All rights reserved.
  Copyright (c) 2023-2026 Igor Pavlov.

Text of the "BSD 3-clause License"
----------------------------------

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its contributors may
   be used to endorse or promote products derived from this software without
   specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR
ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON
ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

---




BSD 2-clause License in 7-Zip code
----------------------------------

  The "BSD 2-clause License" is used for the XXH64 code in 7-Zip.

  XXH64 code in 7-Zip was derived from the original XXH64 code developed by Yann Collet.

  Copyright (c) 2012-2021 Yann Collet.
  Copyright (c) 2023-2026 Igor Pavlov.

Text of the "BSD 2-clause License"
----------------------------------

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR
ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
(INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON
ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

---




unRAR license restriction
-------------------------

The decompression engine for RAR archives was developed using source
code of unRAR program.
All copyrights to original unRAR code are owned by Alexander Roshal.

The license for original unRAR code has the following restriction:

  The unRAR sources cannot be used to re-create the RAR compression algorithm,
  which is proprietary. Distribution of modified unRAR sources in separate form
  or as a part of other software is permitted, provided that it is clearly
  stated in the documentation and source comments that the code may
  not be used to develop a RAR (WinRAR) compatible archiver.

--
