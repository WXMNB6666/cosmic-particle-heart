# Cosmic Particle Heart

一个基于 Three.js 的全屏 3D 粒子心脏交互体验。粒子会组成发光的心形，并根据拖拽、触摸、双击和摄像头手势产生涟漪、旋转与散开效果。

## 预览

这是一个无需构建工具的单页 Web 项目，直接通过静态服务器即可运行。

```bash
python3 -m http.server 8080
```

然后打开 <http://localhost:8080>。

也可以将仓库部署到 GitHub Pages、Netlify 或其他静态托管服务。

## 交互方式

- 拖拽或触摸画面：让粒子产生局部涟漪和漂移
- 双击画面：在聚拢和散开之间切换
- `Front` / `Side` / `Top` / `Elev.`：切换观察视角
- `Scatter`：手动切换粒子散开状态
- `Hand Cam`：启用摄像头手势控制，移动手掌控制粒子，拇指和食指捏合切换散开状态

## 技术栈

- [Three.js](https://threejs.org/)：3D 场景、粒子系统、轨道控制和后期处理
- `UnrealBloomPass`：发光和辉光效果
- [MediaPipe Hands](https://developers.google.com/mediapipe/solutions/vision/hand_landmarker)：浏览器端手势识别
- 原生 HTML、CSS 和 JavaScript：无需打包器和依赖安装

## 摄像头说明

手势控制只会在用户主动点击 `Hand Cam` 后请求摄像头权限。摄像头画面仅用于当前页面中的手势识别，不会上传到服务器。摄像头权限通常要求页面运行在 `localhost` 或 HTTPS 环境中。

## 项目结构

```text
.
├── index.html   # 页面、样式、Three.js 场景和交互逻辑
└── README.md    # 项目说明
```

## 运行环境

建议使用最新版 Chrome、Edge 或 Safari。项目通过 CDN 加载 Three.js 和 MediaPipe Hands，因此首次打开需要网络连接。

## 许可

当前仓库未附加开源许可证。除非获得作者另行授权，请不要将代码用于再发布、商业分发或衍生项目。
