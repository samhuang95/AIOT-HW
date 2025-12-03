# 中央氣象資料爬蟲與戰情室 (AIOT-HW)

## 專案簡介

本專案旨在自動化抓取中央氣象署的中央氣象預報資料，並透過資料處理流程將其轉換為 Excel 報表與 SQLite 資料庫，最後以 Streamlit 建構互動式戰情室 Dashboard 進行視覺化分析。

## 功能特色

- **自動化爬蟲**: 定期抓取最新的中央氣象預報 (F-A0010-001)。
- **資料處理**: 自動解析 JSON 並轉換為結構化數據。
- **多格式儲存**: 支援匯出 Excel (`.xlsx`) 與 SQLite (`.db`)。
- **互動式儀表板**: 使用 Streamlit 與 Plotly 打造專業級氣象戰情室。

## 安裝說明

1. **複製專案**

   ```bash
   git clone https://github.com/samhuang95/AIOT-HW.git
   cd AIOT-HW
   ```

2. **建立虛擬環境 (建議)**

   ```bash
   python -m venv venv
   # Windows
   .\venv\Scripts\activate
   # Mac/Linux
   source venv/bin/activate
   ```

3. **安裝依賴套件**

   ```bash
   pip install -r requirements.txt
   ```

4. **設定環境變數**
   請建立 `.env` 檔案並填入您的 CWA API Token：
   ```text
   API_TOKEN=您的API_TOKEN
   ```

## 操作流程

### 1. 執行爬蟲與資料處理

若只需執行資料抓取與轉檔，可執行：

```bash
python weather_crawler.py
```

執行成功後，目錄下會產生 `weather_data.json`, `weather_report.xlsx`, `weather_data.db`。

### 2. 啟動戰情室 Dashboard

若要開啟網頁介面進行分析：

```bash
streamlit run app.py
```

## 線上展示 (Demo)

🔗 **Streamlit App**: https://aiot-hw-hkxfxavomxk3asw4xdcyyd.streamlit.app/

## 專案結構

- `weather_crawler.py`: 爬蟲主程式
- `data_processor.py`: 資料處理與轉檔邏輯
- `app.py`: Streamlit Dashboard 應用程式
- `requirements.txt`: 專案依賴列表
- `log.md`: 開發日誌

## 開發日誌

詳細的開發歷程請參考 [log.md](./log.md)。
