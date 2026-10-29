# Changelog

本專案記錄經核對的修改與測試結果；未驗證項目不得寫成已修復。

## v0.1.0-rc1 — 2026-10-29（封裝候選版／文件里程碑）

### Changed
- 顯示名稱改為 `Xperia中文鍵盤(Android 15-rc)`。
- 調整 67 個語系對應的應用程式標籤資源。
- `versionName` 設為 `28.3.A.0.3-Android15-rc`。
- `versionCode` 由 `59113475` 更新為 `59113476`。
- 重新封裝及以公開 Android 測試憑證進行 APK v1 簽署。

### Preserved
- 套件識別碼 `com.sonyericsson.textinput.chinese`。
- `minSdkVersion=26`、`targetSdkVersion=28`。
- `classes.dex`、全部原生函式庫、輸入字典及其他資產原始內容。

### Verified (offline only)
- ZIP CRC 完整性檢查通過。
- JAR/APK v1 簽章驗證通過（公開測試憑證，非官方可信簽章）。
- 與手機匯出的先前修改版相比，原始輸入引擎和詞庫未改動；主要內容差異是 `AndroidManifest.xml` 與 `resources.arsc`，以及簽章資料。
- SHA-256：`abdee0414b778ac003ba026b2b09fe41c5a2f3bae7435d7ba3ce3efb61d10982`。

### Not fixed / not verified
- 尚未修復注音候選字凍結與提交延遲。
- 尚未通過 Android 15 安裝、覆蓋、功能及長時間穩定性實機測試。
- 尚未取得完整 APK 及第三方移植成果的公開再散布授權。

參見 [驗證紀錄](docs/VALIDATION-v0.1.0-rc1.md)。
