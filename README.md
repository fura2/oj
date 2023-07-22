## Customized version of oj for personal use

Forked from https://github.com/online-judge-tools/oj

I assume that all the codes written for a contest are placed directly under one directory, with filenames like `a.cpp`, `b.cpp`, and so on.
Note that this does not agree with [the original concept of oj](https://github.com/online-judge-tools/oj/blob/master/DESIGN.md#detailed-design).
```
% tree .
.
├── agc001
│   ├── a.cpp
│   ├── b.cpp
│   ├── c.cpp
│   ├── d.cpp
│   ├── e.cpp
│   └── f.cpp
├── agc002
│   ├── a.cpp
│   ├── b.cpp
│   ├── c.cpp
│   ├── d.cpp
│   ├── e.cpp
│   └── f.cpp
:
```

主に次の機能を追加 / 変更した。

- サンプルテストケースのダウンロード `oj d`
  - ダウンロード時に、既に存在する `test/` ディレクトリを削除するようにした。
- 提出 `oj s`
  - 提出するコードに `#include "template.hpp"` という行が含まれる場合、その行を [template.hpp](https://github.com/fura2/competitive-programming-library/blob/main/library/template/template.hpp) の中身に置換したものが提出されるようにした。
  - [y/N]を入力するステップを省略した。
  - 待ち時間を3秒から0秒に変更した。
  - 提出するコードが [template.cpp](https://github.com/fura2/competitive-programming-library/blob/main/library/template/template.cpp) そのものだった場合、提出を止めてエラーを出力するようにした。(操作ミスによる誤提出の対策)
- テスト入力生成 `oj g/i` とテスト出力生成 `oj g/o`
  - それぞれ、`oj gi` と `oj go` も許容するようにした。
