# check-node

个人学习打卡记录目录。

## 约定

- 每次打卡新建一个 Markdown 文件，按日期命名：`YYYY-MM-DD.md`
- 可从 [`_template.md`](_template.md) 复制模板
- 记录学习和实践过程即可，不需要追求篇幅

## 目录示例

```text
check-node/
├── README.md
├── _template.md
├── 2026-11-17.md
└── 2026-11-18.md
```

## Git 工作流

打卡记录放在独立分支 `checkin`，`main` 用于跟随上游仓库更新。

```bash
# 写打卡记录
git switch checkin
# 新建 check-node/YYYY-MM-DD.md
git add check-node
git commit -m "docs: add YYYY-MM-DD check-in"
git push origin checkin

# 同步上游更新到 main
git switch main
git fetch upstream
git merge upstream/main
git push origin main

# 让打卡分支跟上最新代码
git switch checkin
git merge main
```

## 注意

- 不要提交 API Key、`.env`、个人隐私等敏感信息
- 不要对打卡分支执行 `git reset --hard`、`git clean -fd` 等破坏性操作
