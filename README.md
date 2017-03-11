# 問題說明

希望可以使用 Rx 實作拖拉物件的效果，但目標元素為 svg。

### 描述：

群組拖拉一系列元素(node)，透過 `<g>` 將 `<rect>` 即矩形元素(node)群組為 group，拖拉時再一次修改 g 的 transform 或其他位置屬性完成群組拖拉效果。

### 處理過程

1. 當事件綁定在 `<g>` 時必須要點擊有 node 的地方才會觸發事件。
2. 選擇 將事件綁在 `<svg>`，但拖移時如果滑鼠點擊到有 node 的地方(從 rect 點擊出發) e.clientX 和 Y 取得的數字是錯的。

## 問題點

* 當 Rx.fromEvent 綁定在 parent element 時，為何 children elements 會被觸發？
* 使用 capture behavior 是否能有效解決，該如何正確使用 [useCapture](https://github.com/Reactive-Extensions/RxJS-DOM/blob/master/doc/operators/fromevent.md) 參數？

