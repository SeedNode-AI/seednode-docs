# SeedNode Docs Site (Mintlify)

这是白皮书一致性复核（2026-11-07）之后搬过来的 Mintlify 版白皮书站点源文件，
对应 `Planning/SeedNode_白皮书一致性复核_2026-11-07.html` 里的建议方案。

内容是白皮书 V1 中英文两版的逐段迁移（基于 `../Whitepaper/` 里已核对一致的
docx/pdf 定稿），不是重写。`commercialization.mdx` / `zh/commercialization.mdx`
这一节在白皮书 docx 定稿里原本是空的，内容是从配套 Deck 的"06 — 商业化路径"
页搬过来补上的——2026-11-09 已经过 Charlie 确认定稿，页面里原来的编辑说明
`<Warning>` 已经去掉（生产环境面向投资人的页面不该挂着内部待确认标记）。

## 现状：已经是真实的 GitHub 仓库，已上线

这个仓库已经 push 到 `SeedNode-AI/seednode-docs`，接了 Mintlify 自动部署，
正式域名是 `docs.seednode.ai`。对 `main` 分支的任何提交都会自动触发
Mintlify 重新构建发布，不需要额外的部署步骤。

## 本地校验

这份内容已经用 Mintlify 官方 CLI（`npx mint@latest broken-links`）跑过
链接检查，全部通过，站内中英文互相引用的相对链接没有死链。`mint validate`
需要联网到 Mintlify 云端，在这边的沙箱环境里跑不了，建议 Code 在有正常
网络的环境里跑一次 `npx mint@latest dev` 本地预览确认排版，再推到
Mintlify。
