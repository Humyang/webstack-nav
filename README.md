# 资源导航站点

基于 [WebStack-Hugo](https://github.com/shenweiyan/WebStack-Hugo) 主题构建的静态资源导航站点。

## 技术栈

- **静态站点生成**：[Hugo](https://gohugo.io/)（版本 0.122+）
- **主题**：WebStack-Hugo（`themes/WebStack-Hugo` git submodule）
- **托管部署**：Cloudflare Pages（连接 GitHub 仓库，push 自动构建）

## 本地开发

```bash
# 克隆（含 submodule）
git clone --recurse-submodules <仓库地址>
cd webstack-nav

# 本地预览
hugo server -D
# 访问 http://localhost:1313
```

## 维护导航链接

所有导航链接都在 `data/webstack.yml` 中管理：

```yaml
- taxonomy: 分类名
  icon: fas fa-folder fa-lg
  list:
    - term: 子分类
      links:
        - title: 站点名称
          logo: logo文件名.jpg        # 放在 static/assets/images/logos/ 下
          url: https://example.com/
          description: 站点描述（SEO 用）
```

修改后推送到 GitHub 的 `main` 分支，Cloudflare Pages 会自动重新构建部署。

## 构建部署

- 构建命令：`hugo --gc --minify`
- 输出目录：`public`
