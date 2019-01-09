# Overview
> * [ 環境架設及指令 ](http://git.wz3.bet/howard.hung/Vue_document#%E7%92%B0%E5%A2%83%E6%9E%B6%E8%A8%AD%E5%8F%8A%E6%8C%87%E4%BB%A4)
> * [ 重點分析 ](http://git.wz3.bet/howard.hung/Vue_document#%E9%87%8D%E9%BB%9E%E5%88%86%E6%9E%90)
>   * 指令縮寫  
>   * 列表渲染  
>   * 組件(重覆使用)  
>   * 父子組件  
>   * Slot  
>   * ES5. ES6差異  
>   * 綁定，取值  
>   * 自定義組件指令  
>   * 動態轉換&效果  
> * [ 模塊資源和有用的鏈接 ](http://git.wz3.bet/howard.hung/Vue_document#%E6%A8%A1%E5%A1%8A%E8%B3%87%E6%BA%90%E5%92%8C%E6%9C%89%E7%94%A8%E7%9A%84%E9%8F%88%E6%8E%A5)
> * [Vue js 全文索引](https://cn.vuejs.org/v2/guide/)  

## 環境架設及指令
1. node.js安裝，快速開發免安裝webpack或gulp
2. TortoiseGit安裝
3. "npm install" 安裝基本vue framework
4. "npm run serve" & "npm run dev" 啟動本機瀏覽開發
5. "npm run build" 架站完成發佈
6. "ctrl + c" 解除運行
7. "ctrl + ~" 顯示命令視窗

## 重點分析
- ### 指令縮寫
```
// 縮寫  
v-on:click = @click  
v-bind:href = :href  
v-html = html文本   
// 常用指令  
v-model, v-for, v-show, v-if & v-else, @ click
```

- ### 列表渲染
> * v-for使用 ( [v-for & key] (https://cn.vuejs.org/v2/guide/list.html#key), [v-for & v-if] (https://cn.vuejs.org/v2/guide/list.html#v-for-with-v-if))
> * 變異方法 [ ( push(), splice(), reverse() ...) ] (https://cn.vuejs.org/v2/guide/list.html#%E5%8F%98%E5%BC%82%E6%96%B9%E6%B3%95)

- ### 組件(重覆使用)
```
// index.html
<div id="app">
    <my-cmp></my-cmp>
    <hr>
    <my-cmp></my-cmp>
</div>  
// main.js
Vue.component('my-cmp',{
    data: function(){
        return{
        status: 'Critical'
        }
    },
    template: '<p>Server Status: {{ status }}</p>'
});
new Vue({
    el:'#app'
});
```
> * 聲明響應式  [ >> 官方文件參考 ](https://cn.vuejs.org/v2/guide/reactivity.html#%E5%A3%B0%E6%98%8E%E5%93%8D%E5%BA%94%E5%BC%8F%E5%B1%9E%E6%80%A7)  

- ### 父子組件
```
$emit , props
```
![Emit & Props](./img/01.png "Parent, Child")
> **參考文獻**  
> * [ 关于$emit的用法 ](https://blog.csdn.net/sllailcp/article/details/78595077)    
> * [ 父子組件溝通 - $emit/$on ](https://jeremysu0131.github.io/Vue-js-%E7%88%B6%E5%AD%90%E7%B5%84%E4%BB%B6%E6%BA%9D%E9%80%9A-emit-on/)    
> * [ 父子组件之间的数据通信 - props,$emit](https://segmentfault.com/a/1190000015234117)    

- ### Slot
```
slot = 外部傳遞內容保留的插槽
```
> * Single Slot  
> * Named Slot  
> * Scoped Slot  
> [ >> 官方文件參考 ](https://cn.vuejs.org/v2/api/#slot)

- ### ES5. ES6差異
```
// ES5
data: function () { }
// ES6
data () { }
```

- ### 綁定，取值
> * v-model (雙向綁定，及時)  
> * v-model.lazy (雙向綁定，不及時)  

- ### 自定義組件指令
``` 
// main.js
Vue.directive('highlight' ,{
	bind(el, binding, vnode){
		el.style.backgroundColor = 'green';
    }
});
// App.vue
<p v-highlight>Colors this</p>
``` 
[ >> 更多指令參考 ](https://cn.vuejs.org/v2/api/#%E6%8C%87%E4%BB%A4)

- ### 動態轉換&效果
> * 篩選過濾 Filters  [ >> 官方文件參考 ](https://cn.vuejs.org/v2/guide/filters.html)
> * 合併疊加 Mixins  [ >> 官方文件參考 ](https://cn.vuejs.org/v2/guide/mixins.html)
> * 動畫 Animations (transition & css) [ >> 官方文件參考 ](https://cn.vuejs.org/v2/api/#transition)

## 模塊資源和有用的鏈接
* [ 入門 ](http://vuejs.org/guide/)  
* [ 模板語法 ](http://vuejs.org/guide/syntax.html)  
* [ 活動 ](http://vuejs.org/guide/events.html)  
* [ 計算屬性和觀察者 ](http://vuejs.org/guide/computed.html)  
* [ 類和样式綁定 ](http://vuejs.org/guide/class-and-style.html)  
