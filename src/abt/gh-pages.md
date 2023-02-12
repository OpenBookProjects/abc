# gh-pages
> 免费使用的成本

## background

凡是可以编译为 静态网站 的, 都可以通过 gh-pages/GitHub-Pages 服务来进行免费发布;
只是要小小折腾一下关联的各种资源

## goal
> 必要目标

- [x] 本地编译好, 嘦 git push ,一切就可以自动完成发布
- [x] 而且发布到指定域名

### d0d.fun
> 无门之门, 图书配套域名

- 这书18年触发,19年启动, 计划20完成,21年出版
    - 然后,现在23年了...
- 所以,资源复用原则,先配套给 abc 节目组了

## trace
> 具体推进

- 在 GitHub 创建 pages, 配合 cloudflare 先完成 认证
- clone 仓库(https://github.com/OpenBookProjects/abc)
- 安装好 rust 工具链
- 在 src/ 目录中对应 .md 中撰写内容
    - 要事先在 SUMMARY.md 中追加对应文章入口
    - 当然, 只是草稿时, 不用追加, 这样可以使用 git 完成版本追踪,同时又不自动发布出来
- 使用 `pub.sh` 脚本一建完成发布:
    - 调用 mdbook 指令编译网络-> docs/
    - 复制对应 CNAME 到 docs/
    - 调用 git 指令发布到仓库
    - 触发 gh-actions 完成自动部署
- 



## refer.
> 关键参考

- [验证 GitHub Pages 的自定义域 - GitHub Docs](https://docs.github.com/cn/pages/configuring-a-custom-domain-for-your-github-pages-site/troubleshooting-custom-domains-and-github-pages)
- [Introduction - mdBook Documentation](https://rust-lang.github.io/mdBook/#contributing)
    - 一个更加高速而且不用任何 meta 头信息的 SSG

## logging
> 版本记要

- 230212 ZQ 完成发布
- 221023 ZQ init.