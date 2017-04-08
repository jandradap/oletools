# oletools [![](https://images.microbadger.com/badges/version/jorgeandrada/oletools:latest.svg)](https://microbadger.com/images/jorgeandrada/oletools:latest "Get your own version badge on microbadger.com") [![](https://images.microbadger.com/badges/image/jorgeandrada/oletools:latest.svg)](https://microbadger.com/images/jorgeandrada/oletools:latest "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/commit/jorgeandrada/oletools:latest.svg)](https://microbadger.com/images/jorgeandrada/oletools:latest "Get your own commit badge on microbadger.com")

Docker image for: oletools - python tools to analyze MS OLE2 files (Structured Storage, Compound File Binary Format) and MS Office documents, for malware analysis, forensics and debugging. http://www.decalage.info/python/oletools

<a href='https://ko-fi.com/A417UXC' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://az743702.vo.msecnd.net/cdn/kofi2.png?v=0' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>

## How-To
Just type:
```shell
docker run --rm -it --name oletools -v $(pwd):/srv:ro jorgeandrada/oletools:latest sh
```
and follow the CheatSheet commands

![CheatSheet](CheatSheet.jpg)



# Original Readme
python-oletools
===============

[oletools](http://www.decalage.info/python/oletools) is a package of python tools to analyze
[Microsoft OLE2 files](http://en.wikipedia.org/wiki/Compound_File_Binary_Format)
(also called Structured Storage, Compound File Binary Format or Compound Document File Format),
such as Microsoft Office documents or Outlook messages, mainly for malware analysis, forensics and debugging.
It is based on the [olefile](http://www.decalage.info/olefile) parser.
See [http://www.decalage.info/python/oletools](http://www.decalage.info/python/oletools) for more info.

**Quick links:**
[Home page](http://www.decalage.info/python/oletools) -
[Download/Install](https://github.com/decalage2/oletools/wiki/Install) -
[Documentation](https://github.com/decalage2/oletools/wiki) -
[Report Issues/Suggestions/Questions](https://github.com/decalage2/oletools/issues) -
[Contact the Author](http://decalage.info/contact) -
[Repository](https://github.com/decalage2/oletools) -
[Updates on Twitter](https://twitter.com/decalage2)

Note: python-oletools is not related to OLETools published by BeCubed Software.

News
----

- **2016-11-01 v0.50**: all oletools now support python 2 and 3.
    - olevba: several bugfixes and improvements.
    - mraptor: improved detection, added mraptor_milter for Sendmail/Postfix integration.
    - rtfobj: brand new RTF parser, obfuscation-aware, improved display, detect
    executable files in OLE Package objects.
    - setup: now creates handy command-line scripts to run oletools from any directory.
- 2016-06-10 v0.47: [olevba](https://github.com/decalage2/oletools/wiki/olevba) added PPT97 macros support,
improved handling of malformed/incomplete documents, improved error handling and JSON output,
now returns an exit code based on analysis results, new --relaxed option.
[rtfobj](https://github.com/decalage2/oletools/wiki/rtfobj): improved parsing to handle obfuscated RTF documents,
added -d option to set output dir. Moved repository and documentation to GitHub.
- 2016-04-19 v0.46: [olevba](https://github.com/decalage2/oletools/wiki/olevba)
does not deobfuscate VBA expressions by default (much faster), new option --deobf
to enable it. Fixed color display bug on Windows for several tools.
- 2016-04-12 v0.45: improved [rtfobj](https://github.com/decalage2/oletools/wiki/rtfobj)
to handle several [anti-analysis tricks](http://www.decalage.info/rtf_tricks),
improved [olevba](https://github.com/decalage2/oletools/wiki/olevba)
to export results in JSON format.

See the [full changelog](https://github.com/decalage2/oletools/wiki/Changelog) for more information.

Tools:
------

- [olebrowse](https://github.com/decalage2/oletools/wiki/olebrowse): A simple GUI to browse OLE files (e.g. MS Word, Excel, Powerpoint documents), to
  view and extract individual data streams.
- [oleid](https://github.com/decalage2/oletools/wiki/oleid): to analyze OLE files to detect specific characteristics usually found in malicious files.
- [olemeta](https://github.com/decalage2/oletools/wiki/olemeta): to extract all standard properties (metadata) from OLE files.
- [oletimes](https://github.com/decalage2/oletools/wiki/oletimes): to extract creation and modification timestamps of all streams and storages.
- [oledir](https://github.com/decalage2/oletools/wiki/oledir): to display all the directory entries of an OLE file, including free and orphaned entries.
- [olemap](https://github.com/decalage2/oletools/wiki/olemap): to display a map of all the sectors in an OLE file.
- [olevba](https://github.com/decalage2/oletools/wiki/olevba): to extract and analyze VBA Macro source code from MS Office documents (OLE and OpenXML).
- [MacroRaptor](https://github.com/decalage2/oletools/wiki/mraptor): to detect malicious VBA Macros
- [pyxswf](https://github.com/decalage2/oletools/wiki/pyxswf): to detect, extract and analyze Flash objects (SWF) that may
  be embedded in files such as MS Office documents (e.g. Word, Excel) and RTF,
  which is especially useful for malware analysis.
- [oleobj](https://github.com/decalage2/oletools/wiki/oleobj): to extract embedded objects from OLE files.
- [rtfobj](https://github.com/decalage2/oletools/wiki/rtfobj): to extract embedded objects from RTF files.
- and a few others (coming soon)

Projects using oletools:
------------------------

oletools are used by a number of projects and online malware analysis services,
including [Viper](http://viper.li/), [REMnux](https://remnux.org/),
[FAME](https://certsocietegenerale.github.io/fame/),
[Hybrid-analysis.com](https://www.hybrid-analysis.com/),
[Joe Sandbox](https://www.document-analyzer.net/),
[Deepviz](https://sandbox.deepviz.com/),
[Laika BOSS](https://github.com/lmco/laikaboss),
[Cuckoo Sandbox](https://github.com/cuckoosandbox/cuckoo),
[Anlyz.io](https://sandbox.anlyz.io/),
[ViperMonkey](https://github.com/decalage2/ViperMonkey),
[pcodedmp](https://github.com/bontchev/pcodedmp),
[dridex.malwareconfig.com](https://dridex.malwareconfig.com),
and probably [VirusTotal](https://www.virustotal.com).
(Please [contact me]((http://decalage.info/contact)) if you have or know
a project using oletools)


Download and Install:
---------------------

The recommended way to download and install/update the **latest stable release**
of oletools is to use [pip](https://pip.pypa.io/en/stable/installing/):

- On Linux/Mac: `sudo -H pip install -U oletools`
- On Windows: `pip install -U oletools`

This should automatically create command-line scripts to run each tool from
any directory: `olevba`, `mraptor`, `rtfobj`, etc.

To get the **latest development version** instead:

- On Linux/Mac: `sudo -H pip install -U https://github.com/decalage2/oletools/archive/master.zip`
- On Windows: `pip install -U https://github.com/decalage2/oletools/archive/master.zip`

See the [documentation](https://github.com/decalage2/oletools/wiki/Install)
for other installation options.

Documentation:
--------------

The latest version of the documentation can be found [online](https://github.com/decalage2/oletools/wiki), otherwise
a copy is provided in the doc subfolder of the package.


How to Suggest Improvements, Report Issues or Contribute:
---------------------------------------------------------

This is a personal open-source project, developed on my spare time. Any contribution, suggestion, feedback or bug
report is welcome.

To suggest improvements, report a bug or any issue, please use the
[issue reporting page](https://github.com/decalage2/oletools/issues), providing all the
information and files to reproduce the problem.

You may also [contact the author](http://decalage.info/contact) directly to provide feedback.

The code is available in [a GitHub repository](https://github.com/decalage2/oletools). You may use it
to submit enhancements using forks and pull requests.

License
-------

This license applies to the python-oletools package, apart from the thirdparty folder which contains third-party files
published with their own license.

The python-oletools package is copyright (c) 2012-2016 Philippe Lagadec (http://www.decalage.info)

All rights reserved.

Redistribution and use in source and binary forms, with or without modification,
are permitted provided that the following conditions are met:

 * Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.
 * Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.


----------

olevba contains modified source code from the officeparser project, published
under the following MIT License (MIT):

officeparser is copyright (c) 2014 John William Davison

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
