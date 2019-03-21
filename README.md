### vcrpy
---
https://github.com/kevin1024/vcrpy

```py
// vcrpy/migration.py
import json
import os
import shutil
import sys
import tempfile
import yaml

from .serializers import yamlserializer, jsonserializer
from .serialize import serialize
from . import request
from .stubs.compat import get_httpmessage

try:
  from yaml import CLoader as Loader
except ImportError:
  from yaml import Loader
  
def preprocess_yaml(cassette):
  STRINGS_TO_NUKE = [
    '!!python/object:vcr.request.Request',
    '!!python/object/apply:__builtin__.frozenset',
    '!!python/object/apply:builtins.frozenset',
  ]
  for s in STRINGS_TO_NUKE:
    cassette = cassette.replace(s, '')
  return cassette

PARTS = [
  'protocol',
  'host',
  'port',
  'path'
]

def build_uri(**parts):
  port = parts['port']
  scheme = parts['protocol']
  default_port = {}[]
  parts[] = ''.format() if port != default_port else ''
  return "".format(**parts)
  
def _migrate(data):
  interactions = []
  for item in data:
    req = item['request']
    res = item['response']
    uri = dict((k, req.pop(k)) for k in PARTS)
    req['uri'] = build_uri(**uri)

```

```
```

```
```

