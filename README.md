react-native qrcode 掃描
==============

參考影片:
https://www.youtube.com/watch?v=e7qf9UJvoC0

一開始沒有使用裝置，安裝並編譯成功後，發現 simulator 無法存取 camera


xcode連接iphone:
----------
插上連接線後，選擇 Window->Devices and Simulators  
_第一次無法使用wifi連接，必須接上以後勾選允許使用網路連接_

destination選擇手機裝置
<img width="1305" alt="destination-m" src="https://user-images.githubusercontent.com/24542187/147725543-c8682acc-d128-4152-9c73-72e6c6cfeb6e.png">


* * * 
編譯時遇到錯誤
```
Signing for requires a development team. Select a development team in the Signing & Capabilities editor.
```
新增 Account 並綁定 Identifier
<img width="1338" alt="register-team-m" src="https://user-images.githubusercontent.com/24542187/147725773-b97cd618-7b31-43d0-8c89-1522d6795652.png">

* * *
綁定team時，遇到錯誤 :
> The app identifier "org.reactjs.native.example.qrcode" cannot be registered to your development team because it is not available. Change your bundle identifier to a unique string to try again.

修改Bundle identifier(上圖步驟4.Team的下方): 
ex: org.reactjs.native.example.qrcode => org.reactjs.native.test-patrick.qrcode


* * *
Xcode 遇到「Codesign 要存取鑰匙圈的密碼」:
> 輸入完電腦的登入密碼後，按下"永遠允許"


* * *
could not launch:
此時手機會顯示 **尚未信任開發者**  
```
設定 > 一般 > 裝置管理 > 開發者 APP > Apple Development: xxx@gmail.com > 信任 Apple Development: xxx@gmail.com > 信任
```

