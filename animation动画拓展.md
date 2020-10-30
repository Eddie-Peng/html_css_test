## animation 动画拓展

### 注意（1）：

animation-play-state 也是 animation 的简写属性，但在 -webkit- 中不适用：

```css
animation: myfirst 5s infinite linear paused;
```

即：

```css
animation-name: myfirst;
animation-duration: 5s;
animation-iteration-count: infinite;
animation-timing-function: linear;
animation-play-state: paused;
```

但, 在 -webkit- 中，-webkit-animation-play-state 却是单独的，不能用 -webkit-animation 包含：

```css
-webkit-animation: myfirst 5s infinite linear paused;
```

无效！！！！！

必须写为：

```css
-webkit-animation: myfirst 5s infinite linear;
-webkit-animation-play-state: paused;
```

### 注意（2）：

animation 并不太注重语法顺序（除了【duration / 动画用时】一定在【delay / 动画延时】 之前），但在 -webkit-animation （主要针对 "Safari"）中，不能以 -webkit-animation-name 来结尾：

```css
animation: myfirst 5s linear 2s infinite alternate;
animation: 5s linear 2s infinite myfirst alternate;
animation: 5s 2s infinite alternate linear myfirst;
// etc... 都是可以的
```

但在 Safari 中, 以下语句无法运行：【动画名结尾】

```css
-webkit-animation: 5s linear 2s infinite alternate myfirst;
```

【动画名称】不能作为结尾属性, 以下语句可运行：

```css
-webkit-animation: myfirst 5s linear 2s infinite alternate;
-webkit-animation: 5s linear 2s infinite myfirst alternate;
-webkit-animation: 5s 2s infinite myfirst alternate linear;
```
