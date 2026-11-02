# 大肥鱼表情包素材库

大肥鱼（DeepSeek 鲸鱼娘形象）表情包素材库，共 **322 张 GIF**，分两个包。

| 目录 | 数量 | 说明 |
|------|------|------|
| `大肥鱼/` | 286 | 大肥鱼单人表情包 |
| `大肥鱼和GPT娘/` | 36 | 大肥鱼 × GPT娘 双人表情包 |
| **合计** | **322** | |

单文件最大约 5.7 MB，远低于 GitHub 单文件 100 MB 限制。

## 来源

- 站点：[kiriyuki.com](https://kiriyuki.com) 的 `nekowhale-stickers` 项目
- 采集方式：通过 `scripts/nekowhale_prefetch.py` 预热下载到本地缓存
- 清单版本：manifest `v1009`（2026-10-23 更新）
- 文件名格式：`<编号>_<情绪名>.gif`，例如 `10N01_猫猫搓手.gif`

## 目录结构

```
.
├── README.md
├── 大肥鱼/            # 286 个 gif
│   ├── 10N01_猫猫搓手.gif
│   ├── ...
└── 大肥鱼和GPT娘/     # 36 个 gif
    ├── 2TT01_喝药.gif
    └── ...
```

## 怎么用

本仓库只是「素材库」，本机运行时读取的是缓存目录
`/root/.nekowhale-stickers/packs/`。把仓库里的子目录拷进去即可：

```bash
cp -a 大肥鱼 /root/.nekowhale-stickers/packs/
cp -a 大肥鱼和GPT娘 /root/.nekowhale-stickers/packs/
```

之后 `scripts/sticker_pick.py` 就能直接从本地缓存挑图，不再依赖联网下载。

### 自动同步

工作区里的 `scripts/nekowhale_sync.py` 负责把本仓库的增量同步到本地缓存：

```bash
python3 scripts/nekowhale_sync.py            # 增量同步到 /root/.nekowhale-stickers/packs/
python3 scripts/nekowhale_sync.py --check    # 只检查远程有没有新表情包，不下载
python3 scripts/nekowhale_sync.py --status   # 看本地缓存和远程的对比
```

同步脚本**不会删除**本地缓存里的文件（除非显式加 `--prune`）。

## 同步命令

如果自己 clone 了一份：

```bash
git pull
```

## 注意事项

- 这些 GIF 是公开素材，仓库是公开的（public）。
- 二进制文件，不要用文本编辑器改。
- 仓库体积约 400 MB，clone 需要一定时间；增量同步脚本会走 git 的 blob 过滤，只拉变化的文件。
