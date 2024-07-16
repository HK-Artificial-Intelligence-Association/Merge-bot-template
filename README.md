# MergeBOT 说明

## 1. 简介

该 Bot 通过 Github 工作流对于PR进行合并。推荐在正式工程项目里使用该 Bot。

## 2. 部署

将本仓库的 .github 目录克隆到你想要使用的代码仓库后，新增这三个 label 到你的仓库中：

- waitForMerge

- readyForMerge

- readyForRebase

- do not merge

即可完成部署。


通常，新建 PR 时，为该 PR 添加 waitForMerge 标签；当该 PR 准备合并入相应分支时，添加 readtForMerge 或 readyForRebase 标签，这时 merge-bot 会自动 rebase 该 PR 进入相应分支。即当一个 PR 同时存在 waitForMerge 与 readyForMerge/readyForRebase 时，该PR就会由机器人进行合并。

你可以通过添加 do not merge 标签以避免一不小心错误触发合并流程。
  
如果你想修改合并方式为 merge ，修改 merge-bot.yml 中的 method 即可