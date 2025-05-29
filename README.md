# JWT Decoder

<br/><!-- 換行字元，上下行都得留空 -->

## 簡介
  - 主要提供靜態網頁 (HTML) 來解析 JWT 或 SD-JWT 等格式之字串資料。

<br/>

## 展示網站
- [JWT Decoder](https://iamnarsil.github.io/jwt-decoder/)<br/>

<br/>

## ⌨️ JWT 輸入區

- 可以接受 **JWT** 或 **SD-JWT** 等格式之輸入資料，並且能夠自動針對 JWT 字串進行**分段色彩標示** 🎨。
- 「**複製** 🔵」按鈕：複製輸入格內的 **JWT** 字串至剪貼簿。
- 「**清空** 🔴」按鈕：清空輸入格內的字串資料。

<br/>

## ⌨️ Public Key 輸入區
- 可以接受 **JWK** 格式之公鑰資料，並且能夠自動針對 JSON 字串進行**語法高亮顯示** 🎨。
- 「**複製** 🔵」按鈕：複製輸入格內的 **JWK** 字串至剪貼簿。
- 「**清空** 🔴」按鈕：清空輸入格內的字串資料。
- 輸入「**Public Key** 🗝️」後，將會自動進行「**簽章驗證** ✅❓」。

> [!WARNING]
> 目前僅支援 **P-256** 橢圓曲線加密演算法。

> [!NOTE]
> 驗證結果將會以**文字格式**顯示於「Public Key 輸入區」的「**複製**」按鈕旁，例如：「**簽章驗證成功** ✔️」。

> [!TIP]
> 👉 點擊驗證結果「<ins>**簽章驗證失敗** :x:</ins>」訊息連結，將會以 **氣泡訊息** 💬 形式呈現詳細錯誤資訊。

> [!IMPORTANT]
> 當 JWT payload 內的 **iss** 欄位支援 **```did:key```** 格式時，將會**自動解析**成 JWK 「**公鑰** 🗝️」來呈現，並且也會自動觸發「**簽章驗證** ✅❓」。

<br/>

## 🖥️ Decoded Header 顯示區
- 顯示 JWT Header 基本資訊，並且能夠自動針對 JSON 字串進行**語法高亮顯示** 🎨。

<br/>

## 🖥️ Decoded Payload 顯示區
- 顯示 JWT Payload 基本資訊，並且能夠自動針對 JSON 字串進行**語法高亮顯示** 🎨。
- 「**詳細資料** 🔵」按鈕：於浮空視窗內，以**表格**形式呈現 JWT Payload 各欄位資訊以及相關說明。

> [!CAUTION]
> - 詳細資料表格內出現**異常資訊** ⚠️ 時，例如：*發行日期為未來日期*、*到期日期已過期* … 等，則會以**紅色字體** 🔴 呈現；
> - 同時「**詳細資料** 🔵」按鈕右上角也會出現**紅點標示** 🔴，用以提示使用者。

> [!TIP]
> 👉 點擊詳細資料表格內說明欄的「<ins>**encoded list**</ins>」連結時，將會自動複製 **encoded list** 字串至剪貼簿。

<br/>

## 🖥️ Decoded Disclosures 顯示區
- 顯示 SD-JWT Disclosures 之**明碼**資訊，並且能夠自動針對 Disclosure 明碼格式進行**語法高亮顯示** 🎨。

> [!NOTE]
> Disclosure 明碼格式為 **`["salt","name","value"]`**。

<br/>

## 🖥️ Encoded List 顯示區
- 針對 VC type 欄位為 **StatusList2021Credential** 者，將自動解析 **encodedList** 欄位資料，並且以 **hex dump** 形式呈現。
- 「**手動輸入** 🔵」按鈕：供使用者手動輸入 **encodedList** 資料，以進行狀態清冊驗證。

> [!NOTE]
> - 當 VC type **等於 StatusList2021Credential**時，「**手動輸入** 🔵」按鈕將會隱藏起來 🚫。

> [!IMPORTANT]
> - 手動輸入的 **encodedList** 會被**自動解析**，並且針對 VC **statusListIndex** 欄位所對應到之 byte 位置，也會進行**語法高亮顯示** 🎨。
> - 後續將自動進行「**狀態清冊驗證** ✅❓」，驗證結果將會顯示在「**手動輸入**」按鈕旁，例如：「**狀態驗證成功** ✔️」。

<br/>

## 📜 參考文獻
- [Verifiable Credentials Data Model v1.1](https://www.w3.org/TR/vc-data-model/)
- [Verifiable Credentials Status List v2021](https://www.w3.org/TR/2023/WD-vc-status-list-20230427/)
- [SD-JWT-based Verifiable Credentials (SD-JWT VC)](https://www.ietf.org/archive/id/draft-ietf-oauth-sd-jwt-vc-00.html)
