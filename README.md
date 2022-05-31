# wasa

## Project setup

```
npm install
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

### 作業解說

assets 是放靜態檔案的，components 是放元件，router 是放路由，views 是放各頁面。

首頁 做了一個切換深色及淺色主題的功能，利用 update 辨識預設是否有改變，再用 click 事件做切換

Work1 呈現一個匯率的換算 在 input 框輸入會自動帶入其餘兩個換匯後的結果

Work2 用同一個 component 切換 prop 改變對應的輸入類型

work3 串接 api 將檔案資料放呈現在網頁上
