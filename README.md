tscribe
=======

Produce Word Document, CSV, SQLite and VTT transcriptions using the automatic speech recognition from AWS Transcribe.

[![Build Status](https://travis-ci.com/kibaffo33/aws_transcribe_to_docx.svg?branch=master)](https://travis-ci.com/kibaffo33/aws_transcribe_to_docx)
[![Coverage Status](https://coveralls.io/repos/github/kibaffo33/aws_transcribe_to_docx/badge.svg?branch=master)](https://coveralls.io/github/kibaffo33/aws_transcribe_to_docx?branch=master)

![PyPI - Python Version](https://img.shields.io/pypi/pyversions/tscribe)
[![PyPI version](https://badge.fury.io/py/tscribe.svg)](https://badge.fury.io/py/tscribe)

[![Downloads](https://pepy.tech/badge/tscribe)](https://pepy.tech/project/tscribe)
[![Downloads](https://pepy.tech/badge/tscribe/month)](https://pepy.tech/project/tscribe/month)


# Installation

```bash
pip install tscribe
```


# Results

| Time    | Speaker | Comment     |
| ------- | ------- | ----------- |
| 0:00:03 | spk_0   | Is this on? |
| 0:00:05 | spk_1   | Yep.        |
| 0:00:06 | spk_0   | Great.      |

# keyword_timestamp.json example:

{"Thank": "03:04", "you": "03:04", "for": "02:59", "calling": "00:07",}

# Usage

## Getting started

Simply `import tscribe` and point `tscribe.write(...)` at your `.json` file.

```python
import tscribe

tscribe.write("output.json", format="csv")
```
```
output.csv written in x seconds.
```

## Output formats

Supported output formats include:
* `docx` (default)
* `csv`
* `sqlite`
* `vtt`

```python
import tscribe
tscribe.write("output.json", format="docx")
tscribe.write("output.json", format="csv")
tscribe.write("output.json", format="sqlite")
tscribe.write("output.json", format="vtt")
```
```
output.docx written in x seconds.
output.csv written in x seconds.
output.db written in x seconds.
output.vtt written in x seconds.
```

## Target directory or filename 

You may wish to be explicit in specifying the output filename or directory written to. Use cases may include following a naming convention or operating in a serverless environment.

```python
import tscribe
tscribe.write("output.json", save_as="transcript.docx")
tscribe.write("output.json", save_as="/tmp/transcript.docx")
```
```
transcript.docx written in x seconds.
/tmp/transcript.docx written in x seconds.
```

## Combining format and target

```python
import tscribe
tscribe.write("output.json", format="csv", save_as="output/output.csv")
```
```
output/output.csv written in x seconds.
```
