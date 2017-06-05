# ODK XLSForm.exe
![Platform](https://img.shields.io/badge/platform-Python-blue.svg)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Slack status](http://slack.opendatakit.org/badge.svg)](http://slack.opendatakit.org)

ODK XLSForm.exe is a Windows application for converting an XLSForm into an XForm that is compliant with the [ODK XForms spec](http://opendatakit.github.io/xforms-spec).
   
ODK XLSForm.exe is part of Open Data Kit (ODK), a free and open-source set of tools which help organizations author, field, and manage mobile data collection solutions. Learn more about the Open Data Kit project and its history [here](https://opendatakit.org/about/) and read about example ODK deployments [here](https://opendatakit.org/about/deployments/).

* ODK website: [https://opendatakit.org](https://opendatakit.org)
* ODK forum: [https://forum.opendatakit.org](https://forum.opendatakit.org)
* ODK developer Slack chat: [http://slack.opendatakit.org](http://slack.opendatakit.org) 
* ODK developer Slack archive: [http://opendatakit.slackarchive.io](http://opendatakit.slackarchive.io) 
* ODK developer wiki: [https://github.com/opendatakit/opendatakit/wiki](https://github.com/opendatakit/opendatakit/wiki)

## Please read
* XLSForm.exe does not work on every computer, it does not validate the output XML, and it is not updated frequently. For these reasons, we recommend you use the online [XLSForm converter](http://opendatakit.org/use/xlsform/). 
* When running the app, some users might be [missing the Microsoft Visual C runtime DLL](http://www.py2exe.org/index.cgi/Tutorial#A5.ProvidingtheMicrosoftVisualCruntimeDLL) on their computer. This DLL is not bundled with the exe and there is no easy workaround for these users.

## Using XLSForm.exe
1. Download the zip from the [ODK website](http://opendatakit.org/downloads/download-info/xlsform-for-windows/).
1. Extract it somewhere.
1. Drag an XLSForm onto XLSForm.exe. 
	* A corresponding XForm will appear in the output directory.

## Setting up your build environment
1. Install [Git](https://git-scm.com/downloads) and add it to your path.
1. Fork the xlsform-windows project ([why and how to fork](https://help.github.com/articles/fork-a-repo/)).
1. Clone your fork of the project locally. At the command line:
	* `git clone https://github.com/YOUR-GITHUB-USERNAME/xlsform-windows`
1. Install [Python 2.7.x (32-bit)](https://www.python.org/downloads/).
	* Add `C:\Python27` and `C:\Python27\Scripts` to your path.
1. Install required libraries for pyxform.
	* `pip install xlrd unicodecsv`
1. Download [elementtree (zip)](http://effbot.org/downloads#elementtree).
	* Unzip and run `python setup.py install` in the unzipped directory.
1. Install [py2exe (32-bit for Python 2.7)](http://www.py2exe.org/).

## Building the exe
1. Download the latest release of the [pyxform source](https://github.com/XLSForm/pyxform/releases).
1. In XLSForm.exe's root directory, add the nested `pyxform` directory from pyxform's source.
1. In XLSForm.exe's root directory, run `python setup.py py2exe`.
	* You may get an expected warning about missing modules and binary dependencies.
	* The build is successful when there is a `xlsform.exe` file inside the `dist` directory.
1. Inside the `dist` directory, create an `output` directory.
1. Confirm `xlsform.exe` works dragging a sample file onto the binary. 
	* A corresponding XForm will appear in the `output` directory.
	* You can also run it from the command line to see debugging information, if any.

## Packaging the exe
1. Build the exe and confirm it works.
1. In the `dist` directory, rename the `xlsform.exe` file to `XLSForm.exe`.
1. In the `dist` folder, make sure `output` is empty.
1. Rename the `dist` directory to `XLSForm vx.x.x`.
1. Right-click on `XLSForm vx.x.x`, choose `Send To / Compressed (zipped) folder`. 
	* The resulting zip file is equivalent to the zip available on the [ODK website](http://opendatakit.org/downloads/download-info/xlsform-for-windows/) page.

## Contributing code
Any and all contributions to the project are welcome. ODK XLSForm.exe is used across the world primarily by organizations with a social purpose so you can have real impact!

Issues tagged as [quick win](https://github.com/opendatakit/xlsform-windows/labels/quick%20win) should be a good place to start. There are also currently many issues tagged as [needs reproduction](https://github.com/opendatakit/xlsform-windows/labels/needs%20reproduction) which need someone to try to reproduce them with the current version of ODK XLSForm.exe and comment on the issue with their findings.

If you're ready to contribute code, see [the contribution guide](CONTRIBUTING.md).

## Downloading builds
Current and previous production builds can be found on the [ODK website](http://opendatakit.org/downloads/download-info/xlsform-for-windows).
