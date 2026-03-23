这是什么

- 这个仓库用于维护 Hoffen 的 Hexo 博客（https://hoffen.fun）。
- 分支约定：
  - `hexo`：源码分支（写文章、改配置、改主题都在这里）
  - `main`：发布产物分支（由 GitHub Actions 自动生成并推送，尽量不要手动改）

写作（最常用）

- 新文章放到：`source/_posts/`
- 图片：优先放 `source/img/` 或使用文章外链图（按你习惯）

本地预览（可选）

```bash
npm ci
npx hexo clean
npx hexo server
```

自动部署

- 只要 push 到 `hexo` 分支，会自动触发 GitHub Actions：
  - `npm ci` → `hexo generate` → 把 `public/` 推送到 `main`
  - 同时写入 `CNAME = hoffen.fun`

注意事项

- 不要把 `node_modules/`、`public/`、`.deploy_git/`、`db.json` 提交进仓库（已在 `.gitignore` 中忽略）。
- 如果你需要临时发布草稿，请告诉 Pineo，我会调整 workflow 或发布流程。
