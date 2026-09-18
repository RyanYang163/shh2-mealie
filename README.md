# Mealie

| 项 | 值 |
|---|---|
| 应用 ID | `shh2-mealie` |
| 形态 | Docker 应用（Compose） · WebUI 外开（浏览器新标签） |
| 版本 | 1.0.0 |
| 上游项目 | https://github.com/mealie-recipes/mealie |
| 上游许可证 | AGPL-3.0 |
| 宿主端口 | 18802 |

## 简介

家庭食谱管理：收藏菜谱、生成购物清单、按周排菜。

## 打包

```bash
./build.sh                # 默认 x86_64
./build.sh aarch64        # ARM（Deb 应用）
```

产物在 `build/output/`，同级生成 `<包名>.sha256`。

## 提交前必办事项

- 镜像已核实：`hkotel/mealie:v3.27.0` 托管在 Docker Hub，提供 amd64 + arm64，最近更新 2026-09-17 —— **满足 H14**。
- ⚠️ 注意：Mealie 官方已迁到 GHCR，Docker Hub 上没有官方命名空间。本项使用的是活跃维护的社区镜像 `hkotel/mealie`（早期官方命名空间）。若审核方不接受社区镜像，更稳妥的做法是把官方 GHCR 镜像同步到自己的 Docker Hub 账号下再引用。
- ⚠️ 上游已进入 v3.x（原调研资料里的 v2 信息已过时），本项锁定 v3.27.0，升级时改 `docker-compose.yml` 的 tag 即可。
- 官方镜像自带 HEALTHCHECK，compose 中未重复定义。
- 社区反馈冷启动较慢，首屏 ≤5 秒需真机实测。
- [ ] 真机安装、启动、停止、卸载残留四项实测
- [ ] 首屏加载 ≤ 5 秒（指引 H10）
- [ ] x86_64 与 aarch64 分别构建并测试（指引 H7）
- [ ] 提交前跑一遍指引 13.9 上架前自查清单

## 隐私政策

见 [PRIVACY.md](./PRIVACY.md)（对应审核项 C3–C8）。

## 许可证与出处

本仓库**仅包含 TOS 平台集成所需的配置文件与打包脚本**，应用本体的源码与二进制来自上游项目：https://github.com/mealie-recipes/mealie

上游许可证：**%s**。本封装保留上游许可证声明，未修改上游代码（Deb 形态下按上游许可证要求随包提供 LICENSE）。

应用名称与图标为上游项目的标识；本仓库图标为自行绘制的简易图形，不含上游商标元素（对应审核项 H19）。
