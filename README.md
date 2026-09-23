# 高考数据集副本

供「志愿通」数据管道自动拉取的镜像：数据集源（HF 镜像）的 `robots.txt` 禁止抓取，
所以每年人工下载一次，再用 `pipeline/mirror.py` 同步到这里，之后就能全自动。

```
data/<年>/<省>/<dataset>.csv     # 对应 url_template 的 {year}/{prov}/{dataset}
```

```bash
export GAOKAO_DATA_BASE=https://raw.githubusercontent.com/botonwa83-byte/gaokao-data/main/data
python -m pipeline.run --all --year 2026        # 31 省自动下载
```

数据来源：公开高考数据集 + 各省考试院公告（人工下载后上传），本仓库只做副本。
