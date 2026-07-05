# 分行據點地圖產生器 (Branch Locator Map)

> 把 Excel 地址一鍵放上互動地圖

## 🎯 給誰用
- 金融機構行政人員
- 連鎖企業多據點管理
- 想把地址清單視覺化的人

## ✨ 功能
- 📂 上傳 Excel(.xlsx)地址清單
- 🗺️ 自動轉成互動地圖(Leaflet)
- 🔍 智慧地址清理(剝離里鄰行政區)
- 🛡️ 多層次地理編碼 fallback(Nominatim API)
- ⚙️ API 限流保護(1.2 秒/請求)

## 🧰 技術棧
- **Leaflet.js** — 地圖呈現與標記管理
- **SheetJS (xlsx.js)** — 瀏覽器端 Excel 解析
- **Nominatim API (OpenStreetMap)** — 免費地理編碼服務

## 📊 資料格式
Excel 欄位配置:
- **B 欄**:據點名稱
- **N 欄**:地址(支援穿插郵遞區號與行政區格式)

## 🚀 使用方式
1. 開啟 `map_viewer.html`
2. 點「載入檔案」選 `社地址.xlsx`
3. 等待程式處理(每筆 1.2~5 秒,視資料筆數而定)
4. 處理完成後,點地圖標記可查看詳細資訊

## 🧠 地址處理邏輯
採多層次 fallback 確保高定位成功率:
1. **完整地址**(含據點名稱+行政區)
2. **據點簡搜**(剝離行政區)
3. **據點去後綴**(去除「分行」「辦事處」等詞)
4. **簡化據點**(只取據點名+縣市)
5. **地區搜尋**(以鄉鎮區為單位)
6. **縣市 fallback**(最終保險)

## 🌐 Demo
GitHub Pages: https://rock903400-byte.github.io/cu-branch-locator-map/

## License
MIT
