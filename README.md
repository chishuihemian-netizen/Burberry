# 上传到 GitHub 后部署到 Cloudflare

这个文件夹内一共不足 60 个文件，可以在 GitHub 网页端一次上传。

## 上传

1. 解压本压缩包。
2. 打开 GitHub 仓库 `chishuihemian-netizen/Burberry` 的主页。
3. 删除仓库中现有的 **Burberry** 单个文件（它不是网站目录）。
4. 点击 **Add file → Upload files**，将解压后看到的 `public` 文件夹、`wrangler.jsonc`、`.gitignore` 和 `README.md` 一起拖入上传区并提交。
5. 上传完成后，仓库根目录必须是：

```text
public/
wrangler.jsonc
.gitignore
README.md
```

## Cloudflare

在现有 Cloudflare Workers 构建设置中保持：

```text
Deploy command: npx wrangler deploy
Root directory: 留空
```

不要设置 `.` 为 Output Directory。根目录的 `wrangler.jsonc` 已固定资源目录为 `./public`，Cloudflare 只会部署 `public/`，不会读取 `.git`。

投票后台需要另行部署，当前网页可以正常预览，投票按钮会显示尚未启用。
