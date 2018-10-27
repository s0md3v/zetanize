<h1 align="center">
  <br>
  <a href="https://github.com/s0md3v/zetanize"><img src="https://image.ibb.co/i9w7Fq/zetanize-logo.png" alt="zetanize"></a>
  <br>
  zetanize
  <br>
</h1>

<h4 align="center">HTML Form Parser For Humans</h4>

<p align="center">
  <a href="https://github.com/s0md3v/zetanize/releases">
    <img src="https://img.shields.io/github/release/s0md3v/zetanize.svg">
  </a>
  <a href="https://github.com/s0md3v/zetanize/issues?q=is%3Aissue+is%3Aclosed">
      <img src="https://img.shields.io/github/issues-closed-raw/s0md3v/zetanize.svg">
  </a>
</p>

### Introduction
It's very easy to make HTTP requests in python, thanks to urllib and requests. However, there was no way to submit HTML forms on the go, well now there is.

### Documentation
```python
from zetanize import zetanize
forms = zetanize(html)
```

Well that's it! Just feed zetanize a HTML document and it will give you a dict of actionable form data.<br>
Let's parse https://google.com for getting familiar:
```python
from requests import get
from zetanize import zetanize

html = get('https://google.com').text
forms = zetanize(html)
```

Here's the output:

```json
{
  "0": {
    "action": "/search", 
    "inputs": [
      {
        "type": "hidden", 
        "name": "ie", 
        "value": "ISO-8859-1"
      }, 
      {
        "type": "hidden", 
        "name": "hl", 
        "value": "en-IN"
      }, 
      {
        "type": "hidden", 
        "name": "source", 
        "value": "hp"
      }, 
      {
        "type": "hidden", 
        "name": "biw", 
        "value": ""
      }, 
      {
        "type": "hidden", 
        "name": "bih", 
        "value": ""
      }, 
      {
        "type": "", 
        "name": "q", 
        "value": ""
      }, 
      {
        "type": "submit", 
        "name": "btnG", 
        "value": "Google Search"
      }, 
      {
        "type": "submit", 
        "name": "btnI", 
        "value": "I"
      }, 
      {
        "type": "hidden", 
        "name": "gbv", 
        "value": "1"
      }
    ], 
    "method": "get"
  }
}
```
