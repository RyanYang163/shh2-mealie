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

- ⚠️ 官方文档推荐使用 GHCR 镜像；H14 要求镜像源为 Docker Hub，提交前必须确认该镜像在 Docker Hub 上可用，否则会被驳回。
- ⚠️ 镜像 TAG 未能核实（本机无法访问 Docker Hub），已置为 TAG-VERIFY，build.sh 会拒绝构建，请先填入经验证的版本号。
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
