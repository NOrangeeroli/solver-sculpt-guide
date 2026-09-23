# Solver Sculpt · 可搜索求解器图解

中文交互式文档：五层 solver 组件、跨方程结构、DSL、L1/L2 supernet、联合训练、多网格、CFL 控制与预算剪枝。

网站：https://norangeeroli.github.io/solver-sculpt-guide/

## 范围

技术内容对应 `NOrangeeroli/meta-pde-solver` 的代码快照 `7b302f507d3ef6707be63ff099b91376a6573adb`。这是独立文档仓库，不包含研究代码、训练数据或凭据。文档中的源码链接需要相应仓库的访问权限。Gate 和预算交互是教学示意，不是新的科学实验结果。

## 本地预览与检查

```sh
python3 -m http.server 8769 --bind 127.0.0.1
node --check content.js
node --check app.js
```

无需构建或外部依赖。GitHub Pages 从 `main` 分支根目录发布；推送更新后自动重建。`.nojekyll` 保持静态文件原样发布。

页面包含 11 个章节，提供层级切换、候选对比、稀疏 gate 与预算演示、可复制代码和可下载配置。布局参考 [HyperBench 文档](https://norangeeroli.github.io/hyperbench-pages/#overview)。

## CFL 与时间步文档更新

控制器章节区分可学习 CFL、状态相关选步与完整策略搜索，并分别映射 decision_graph 与 control_plan 的 L0–L4。简单 solver 算例附有 T=0.03 的实际两步 CFL rollout。新增 Python 示例已验证五层选步一致性及最终状态 / 接受次数。核查 budget-search 分支至 `26e6f0d73`，相关模块相对原文档快照未改变；实验结果和其他工作区未提交控制 IR 草稿不计为本文已发布能力。
