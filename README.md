# ODK XLSForm.exe
![Platform](https://img.shields.io/badge/platform-Python-blue.svg)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![Slack status](http://slack.opendatakit.org/badge.svg)](http://slack.opendatakit.org)

## Please read
* XLSForm.exe does not work on every computer, it does not validate the output XML, and it is not updated frequently. For these reasons, we recommend you use the online [XLSForm converter](http://opendatakit.org/use/xlsform/). 
* When running the app, some users might be [missing the Microsoft Visual C runtime DLL](http://www.py2exe.org/index.cgi/Tutorial#A5.ProvidingtheMicrosoftVisualCruntimeDLL) on their computer. This DLL is not bundled with the exe and there is no easy workaround for these users.

## Using XLSForm.exe
1. Download the zip from the [ODK website](http://opendatakit.org/downloads/download-info/xlsform-for-windows/).
1. Extract it somewhere.
1. Drag an XLSForm onto XLSForm.exe. 
	* A corresponding XForm will appear in the output directory.

## Build requirements
1. Install [Python 2.7.x (32-bit)](https://www.python.org/downloads/).
	* Add `C:\Python27` and `C:\Python27\Scripts` to your path.
1. Install required libraries for pyxform.
	* `pip install xlrd unicodecsv`.
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
1. The resulting zip file is equivalent to the zip available on the [ODK website](http://opendatakit.org/downloads/download-info/xlsform-for-windows/) page

## Contributing code
Any and all contributions to the project are welcome. ODK XLSForm.exe is used across the world primarily by organizations with a social purpose so you can have real impact!

Issues tagged as [quick win](https://github.com/opendatakit/xlsform.exe/labels/quick%20win) should be a good place to start. There are also currently many issues tagged as [needs reproduction](https://github.com/opendatakit/xlsform.exe/labels/needs%20reproduction) which need someone to try to reproduce them with the current version of ODK XLSForm.exe and comment on the issue with their findings.

If you're ready to contribute code, see [the contribution guide](CONTRIBUTING.md).

## Downloading builds
Current and previous production builds can be found on the [ODK website](https://opendatakit.org/downloads/download-info/odk-collect-apk).