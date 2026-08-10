# bashrc

在新的 CLI 環境快速套用一份基本的 bash 設定。

## 使用方式

```bash
source <(npx louisje/bashrc)
```

會依目前環境動態組合並輸出一段 bash 設定，套用到目前的 shell。

另一種用法：在新環境直接產生一份現成的 `~/.bashrc`：

```bash
npx louisje/bashrc > ~/.bashrc
```

## 目前內容

- 若 `~/.local/bin` 不在 `$PATH` 中，加入到 `$PATH` 最前面
- `alias sudo='sudo '`：讓 `sudo` 後面接的指令也能套用 alias 展開
- `alias ..='cd ..'`
- 若 `ll` 指令不存在，設定 `alias ll='ls -Flart --color'`
- 若 `z` 指令不存在，設定 `alias z='cd'`

之後會依需求持續補上更多 alias / prompt / function。

## 開發

進入點：`bin/bashrc.js`

要新增設定區塊時，在 `sections` 陣列裡加入新的 function，回傳要輸出的 bash 內容字串即可。

本地測試：

```bash
node bin/bashrc.js
# 或
source <(node bin/bashrc.js)
```
