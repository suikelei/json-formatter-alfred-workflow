# JSON Formatter

An alfred workfow to formatter strings to beautiful JSON to you clipboard.

### Usage
1. Default `Ctrl + Alt + J` to formatter your clipboard content to standard JSON.
2. Active Alfred and enter default keyword `json`, paste your content, done.

### Customize

The core python script in the workflow looks like:

```python
# -*- coding:utf-8 -*-

import sys
import json
from collections import OrderedDict

query = sys.argv[1]

# 对json字段进行重新排序
# print(json.dumps(json.loads(query), ensure_ascii=False, encoding='UTF-8', sort_keys=True, indent=4, separators=(',', ': ')))

# 保持json字段的顺序
print(json.dumps(json.loads(query,object_pairs_hook=OrderedDict), ensure_ascii=False, encoding='UTF-8', sort_keys=False, indent=4, separators=(',', ': ')))
```

If you are familiar with python, edit the params of `json.dumps()` to custom json format.
