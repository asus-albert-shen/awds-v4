# ASUS Web Design System

## Readme

此檔案主要用於建立 ASUS web style 所廣泛使用的字級用表，透過連結此檔中的 Text style 來達到各專案與網頁的用字一致性，以下簡單介紹檔案內容與用法

在此檔案中將 Text Style 以兩類型呈現分別為 Primitives 以及 Semantics

### Primitives token

以字型特徵的集合來命名各級字的 Token，目的為呈現最基礎、最原始的數值元素

### Semantics token

由 Primitives token 依專案需求再次收斂而得之，並以用途特徵作為 Token 命名，因團隊專案內容大部分為一般營銷頁面，因此 Semantic 可滿足大部分頁面設計需求

### Customize token

若需應用的專案或頁面目的主要非營銷目的，如類 CRM 系統，Dashboard 等用途可斟酌自行利用 Primitives token 自行搭配出符合需求的 Semantic 字級表

### ASUS 內部員工使用方式

不同部門的設計師若需使用此字級表

#### 方法一直接在 ASUS 組織裡嵌入

到 Figma 檔案中左側的 Assets 頁籤中，開啟 Libraries (Book icon) 對話視窗
於對話視窗中左側列表中選擇 Your organization 並找到 awds-fonts-v4 (或直接搜尋該檔名)
在 awds-fonts-v4 檔案上點選 Add to file 即成功加入此字級表至檔案中使用
此方法的字級表未與我們團隊進行共用，因此後續有所更新時將可即時反應

#### 方法二

複製到所需使用的 Figma 專案中
到 Figma 檔案中點選左上角 Figma logo 旁邊的下拉箭頭
選取 Save a local copy 並存到本機硬碟中
回到 Figma 的專案大廳中，選擇你要放置檔案的專案資料夾
點擊右上角的 + Create 按鈕中的 import
選取剛剛存到本機的 Figma 檔案並 import
到你所需要嵌入的檔案中於左側找到 Assets 頁籤並嵌入剛剛匯入的字級表檔案

### Data同步處理與備份

修改字級需使用plugin “Studio token for Figma”(後續稱"Studio token")
所有 font style 以及 Variable library 皆有串接上述 plugin
Studio token 有串接 Github，可經由 Github 上的 Json 檔進行編輯、新增以及刪除等

### CSS view in Dev mode

由於 Figma text style 的分層方式, 無法有效的解決 Text Style 與 Code token 的差異, 因此提供如何將 Code token 對應到 Dev mode 中 Text Style 的名稱
進到 Dev mode 後點選要觀察的文字物件後, 會在右側 Typography 中看到 CSS 參考, Figma 會將設計系統中的 Text Style 轉成 CSS 註解的方式呈現 (如右圖第 3 行)

Primitives token 可以忽略前面斜線的分層, 專注於後最後一組連字, 如右圖 1, 該連字為該字樣的 token name, 即為 “ro-rg-24"

Semantics token 的部份分成兩組, 若為無依頁面斷點分層的 Token 則與 Primitives token 一樣方式, 帶有 fluid 前綴的需參考到最後一個分層並把分層的”/”改為”-”. 如右圖 2 所示, 完整 token name 為 “fluid-heading-09-top-split”

### Glossary

Primitive tokens (基礎標記)主要以樣式本身特徵命名，如 $blue-60, $fontype-01, $space-01...etc.另別名 Global tokens、Reference tokens、Core tokens、Root tokens、Base tokens、Basic tokens、Foundation tokens、Choice tokens、Option tokens、Meta tokens
Semantic tokens (語意標記)以定義各樣式的用途，目的是減少樣式上的選擇，加速製圖上的效率，如 $color-primary, $padding-sm, $radius-pill...etc另別名 Alias tokens、System tokens、Application tokens、Purpose tokens、Decision tokens、Applied tokens
Scoped tokens (範圍標記)根據專案、模組、頁面等因風格或特殊性另外製作的令牌，非必要性建置，如 $button-color-background-primary-hover, $button-color-label-hover, $header-text-primary-normal...etc
Token nested (巢化標記結構, 嵌套式標記結構)建立 Token 目的是標準化樣式，因此在標記間可互相嵌套，基於Token層級，應由小範圍的標記往大範圍的標記嵌套，基本會式 Scoped token {Semantic token (Primitive token)}的方式，若在語意上無法滿足用途亦可用Scoped token {Primitive token}等等，避免反向嵌套如 Primitive token{Semantic token}For instance: $button-color-background-primary-hover = $color-primary-hover = $blue-50 = #0051A8