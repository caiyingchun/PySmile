## PySmile

Encode/Decode SMILE format objects

Based on:

http://wiki.fasterxml.com/SmileFormat

and

https://github.com/brianm/libsmile



## Install:

```bash
python setup.py clean build test && python setup.py install
```

or from pypi (https://pypi.python.org/pypi/pysmile):

```bash
pip install pysmile
```

## Example Usage:

```python
>>> import pysmile
>>> o = {'a': 1, 'b': [2, 3, 4], 'c': {'d': {'e': 4.20}}}
>>> b = pysmile.encode(o)
>>> print repr(b)
':)\n\x03\xfa\x80a\xc2\x80c\xfa\x80d\xfa\x80e(fL\x19\x04\x04\xfb\xfb\x80b\xf8\xc4\xc6\xc8\xf9\xfb'

>>> d = pysmile.decode(b)
>>> print d
{u'a': 1, u'b': [2, 3, 4], u'c': {u'd': {u'e': 4.2}}}

>>> assert d == o
```
