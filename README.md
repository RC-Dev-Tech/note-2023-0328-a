# ![](https://drive.google.com/uc?id=10INx5_pkhMcYRdx_OO4rXNXxcsvPtBYq) Error: listen EADDRINUSE: address already in use
> ##### 問題記錄.

<br>

<!--ts-->
## 目錄
* [簡介](#簡介)
* [參考資料](#參考資料)
<!--te-->

---
<br>

## 簡介
有的時候會遇到在寫某個範例的時候，因為執行緒把某個Port號佔去了，導致程式在運行的時候發生錯誤.<br>
以下的方法，可以找到Port號被哪一個執行緒給佔去，然後該怎麼把他釋放掉.

**Mac** <br>
**lsof -i tcp:port_number**   &nbsp;&nbsp;  //檢查目前port號被哪一個執行緒佔據 <br>
**kill -9 PID**               &nbsp;&nbsp;  //把該執行緒給刪除, PID為執行緒的ID. <br>

<br>

**範例:** <br>
**lsof -i tcp:3000** <br>
> COMMAND   PID        USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME<br>
> node    66856       ricky   22u  IPv6 0xdc31e3995b3a330b      0t0  TCP *:exlm-agent (LISTEN)<br>
**kill -9 66856**<br>

---
<br>

## 參考資料
* [[前端筆記] 使用 Node.js 時噴錯 -Error: listen EADDRINUSE: address already in use 127.0.0.1:3000](https://bonnieyf.medium.com/%E5%89%8D%E7%AB%AF%E7%AD%86%E8%A8%98-%E4%BD%BF%E7%94%A8-node-js-%E6%99%82%E5%99%B4%E9%8C%AF-error-listen-eaddrinuse-address-already-in-use-127-0-0-1-3000-e9f14532ad50) <br>

---
<!--ts-->
#### [目錄 ↩](#目錄)
<!--te-->
---