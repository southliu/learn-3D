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

# GUI

## 快捷键
```
h - 切换开关
```
设置gui.hide()隐藏之后需要按两下`h`来唤醒。