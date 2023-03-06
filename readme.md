# 3D学习项目

## Animate - 旋转动画
```JS
// Clock
const clock = new THREE.Clock()

// Animations
const tick = () => {
    // Clock
    const elapsedTime = clock.getElapsedTime()
    
    mesh.position.x = Math.cos(elapsedTime)
    mesh.position.y = Math.sin(elapsedTime)

    // Render
    renderer.render(scene, camera)

    window.requestAnimationFrame(tick)
}
```

# 性能优化

## 设置像素比
```js
const renderer = new THREE.WebGLRenderer({ canvas })
// 设置像素比
renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2))
```

## 处理纹理
```js
const loadingManager = new THREE.LoadingManager()
const textureLoader = new THREE.TextureLoader(loadingManager)
const colorTexture = textureLoader.load('/textures/checkerboard-8x8.png')
/**
 * THREE.NearestFilter 最近点采样
 * THREE.LinearFilter 线性采样 默认值
 * minFilter 缩小滤镜（例如32X32的纹理映射到16X16的像素空间）
 * magFilter 放大滤镜（例如16X16的纹理映射到32X32的像素空间）
 */
// colorTexture.minFilter = THREE.NearestFilter
colorTexture.magFilter = THREE.NearestFilter
```

## gltf压缩
```
https://gltf.report
```

# GUI

## 快捷键
```
h - 切换开关
```
设置gui.hide()隐藏之后需要按两下`h`来唤醒。