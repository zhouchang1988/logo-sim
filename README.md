# LOGO 语言模拟器

纯前端 LOGO 语言模拟器，无需服务器，打开 `index.html` 即可使用。

## 功能

- 完整的 LOGO 语言词法分析、语法解析和解释执行
- 海龟绘图动画，支持速度调节
- 7 个内置示例程序
- 帮助面板，随时查阅命令

## 支持的命令

| 命令 | 缩写 | 参数 | 说明 |
|------|------|------|------|
| FORWARD | FD | 距离 | 向前移动 |
| BACK | BK | 距离 | 向后移动 |
| RIGHT | RT | 角度 | 右转 |
| LEFT | LT | 角度 | 左转 |
| PENUP | PU | - | 抬笔 |
| PENDOWN | PD | - | 落笔 |
| CLEARSCREEN | CS / CLEAR | - | 清屏并重置 |
| REPEAT | - | 次数[命令] | 重复执行，支持嵌套 |

注释以 `;` 开头，不会被执行。

## 使用方式

双击 `index.html` 在浏览器中打开，或：

```bash
# macOS
open index.html

# Linux
xdg-open index.html

# Windows
start index.html
```

在代码编辑器中输入 LOGO 代码，点击"运行"或按 `Ctrl/Cmd + Enter` 执行。

## 示例

```
REPEAT 4[FD 100 RT 90]                ; 正方形
REPEAT 3[FD 100 RT 120]               ; 三角形
REPEAT 5[FD 100 RT 144]               ; 五角星
REPEAT 36[FD 10 RT 10]                ; 圆形
REPEAT 10[REPEAT 4[FD 50 RT 90] RT 36] ; 嵌套正方形
REPEAT 8[REPEAT 4[FD 60 RT 90] RT 45]  ; 花朵
```

## 技术实现

- 单 HTML 文件，零依赖
- JavaScript 实现词法分析器（Lexer）、语法分析器（Parser）、解释器（Interpreter）
- Canvas 2D 绘图，支持逐行动画
- Claude 设计风格 UI
