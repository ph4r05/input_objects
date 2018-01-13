# Input object library

Uniform API for reading from multiple different sources.

Contains reconnecting reading file like object for uninterrupted stream reading of remote files.

```python
import requests, lz4framed, input_obj
url = 'https://ph4r05.deadcode.me/static/lz4/certificates.20171002T020001.15.json.lz4'
iobj = input_obj.ReconnectingLinkInputObject(url=url, timeout=5*60, max_reconnects=1000)
for idx, chunk in enumerate(lz4framed.Decompressor(iobj)):
    print(chunk)
```

## Pip package

```
pip install -U pip setuptools twine
python setup.py sdist
twine upload dist/*
```


