# SeedNode Docs Site (Mintlify)

这是白皮书一致性复核（2026-11-07）之后搬过来的 Mintlify 版白皮书站点源文件，
对应 `Planning/SeedNode_白皮书一致性复核_2026-11-07.html` 里的建议方案。

内容是白皮书 V1 中英文两版的逐段迁移（基于 `../Whitepaper/` 里已核对一致的
docx/pdf 定稿），不是重写。唯一的例外是 `commercialization.mdx` /
`zh/commercialization.mdx`——这一节在白皮书 docx 定稿里是空的，内容是从配套
Deck 的"06 — 商业化路径"页搬过来补上的，文件里用 `<Warning>` 标出来了，
需要 Charlie 确认。

## 这不是 git 仓库（还不是）

这个文件夹目前只是本地文件，还没有 `git init`。按项目协作分工（Cowork 做
方案/文案，Code 做代码/git/部署），把这个文件夹变成可以被 Mintlify
部署的 GitHub 仓库这一步，建议交给 Code 窗口做：

1. `cd` 进这个文件夹，`git init`，`git add -A`，提交一次初始版本。
2. 在 `SeedNode-AI` 这个 GitHub 组织下建一个新仓库（建议叫
   `seednode-docs`，和主仓库 `SeedNode-AI/SeedNode` 分开，避免跟
   `apps/web` 的 Vercel 部署、pnpm workspace 产生任何耦合）。
3. push 上去。

## 需要 Charlie 自己做的事（没法由 Claude 代劳）

1. 去 mintlify.com 注册账号（免费 Starter 档即可，已核实含自定义域名）。
2. 在 Mintlify 后台用 GitHub 账号连接刚才新建的 `seednode-docs` 仓库——
   连上之后 Mintlify 会自动检测根目录的 `docs.json` 并部署，网站立刻可访问
   （先是一个 mintlify.app 的临时域名）。
3. 在 Mintlify 后台的 Custom Domain 设置里填 `docs.seednode.ai`，
   它会给一条 CNAME 记录，照着在你的域名服务商（Cloudflare/Namecheap等，
   取决于 seednode.ai 的 DNS 托管在哪）里加一条 CNAME 解析记录。
4. 等 DNS 生效（通常几分钟到几小时），`docs.seednode.ai` 就是最终地址。

## 本地校验

这份内容已经用 Mintlify 官方 CLI（`npx mint@latest broken-links`）跑过
链接检查，全部通过，站内中英文互相引用的相对链接没有死链。`mint validate`
需要联网到 Mintlify 云端，在这边的沙箱环境里跑不了，建议 Code 在有正常
网络的环境里跑一次 `npx mint@latest dev` 本地预览确认排版，再推到
Mintlify。
