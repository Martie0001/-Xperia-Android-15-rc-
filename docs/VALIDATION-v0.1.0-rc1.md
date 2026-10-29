# v0.1.0-rc1 APK 驗證紀錄

日期：2026-10-29（台灣時間）

> 本文件只描述已完成的**離線檢查**及其限制。它不是 Android 15 相容性認證，也不是選字凍結已修復的證明。

## 驗證對象

- 成品檔名：`Xperia中文鍵盤(Android 15-rc).apk`
- 位元組大小：`67,054,286`
- SHA-256：`abdee0414b778ac003ba026b2b09fe41c5a2f3bae7435d7ba3ce3efb61d10982`
- 對照來源：使用者從 Xperia 1 V 匯出的先前修改版 `Xperia中文鍵盤.apk`
- 對照來源 SHA-256：`3a1f200fefcce82225a388657e347c6b259d7f6b9f2965b5f514c99f7f285ad0`

## 已核對的項目

| 檢查 | 結果 | 範圍及限制 |
| --- | --- | --- |
| SHA-256 | PASS | 直接對使用者上傳的 RC APK 計算；與建置紀錄一致 |
| ZIP CRC | PASS | 所有 ZIP 成員可讀取，未檢出 CRC 錯誤 |
| ZIP 項目數 | 1,854 | RC 與先前修改版相同 |
| JAR/APK v1 簽章 | PASS | `jarsigner -verify` 顯示 jar verified |
| 簽署憑證 | Android 公開測試憑證 | 自我簽署、非 Sony 官方、不是正式可信發布簽章 |
| 與對照版檔案差異 | 已核對 | 內容改動：`AndroidManifest.xml`、`resources.arsc`、`META-INF/MANIFEST.MF`；簽章檔由 `CERT.*` 改為 `ANDROIDT.*` |
| `classes.dex`、原生函式庫、詞庫 | 未修改 | 與對照 APK 的逐成員內容比對一致 |

簽章工具另提示憑證為自我簽署、無時間戳，**不等於**已建立受信任的發行者身分。此處沒有宣稱 APK v2／v3 簽章通過。

## 依建置紀錄核對的版本資訊

- 應用程式顯示名稱：`Xperia中文鍵盤(Android 15-rc)`
- `versionName`：`28.3.A.0.3-Android15-rc`
- `versionCode`：`59113476`
- `package`：`com.sonyericsson.textinput.chinese`
- `minSdkVersion`：`26`
- `targetSdkVersion`：`28`
- 67 個語系標籤參照：建置紀錄列為 PASS。

上述 Manifest/資源語意值及 67 處資源參照，依建置時產出的驗證紀錄列載；本次獨立複驗的重點為檔案完整性、簽章與成員內容差異。

## 未完成的實機驗收

- [ ] Xperia 1 V／Android 15 可安裝及啟用
- [ ] 可安全覆蓋舊版且保留使用者資料（如不允許，停止測試）
- [ ] 注音輸入、選字提交正常
- [ ] 下一字預測正常
- [ ] 按鍵震動正常
- [ ] 個人詞庫及偏好設定保留
- [ ] LINE、Discord、ChatGPT 等多 App 輸入正常
- [ ] 連續使用時未重現候選字凍結

**已知問題：** 候選字偶發卡住、選字預覽停留、文字提交延遲；原因未確認，本版未調整候選字程式碼。

## 發布限制

APK 使用第三方修改版為基礎；原始內容及移植成果的公開再散布權限尚未確認。因此本次僅發布技術文件，不提供 APK 附件或重封裝程式。詳見 [THIRD_PARTY_NOTICES.md](../THIRD_PARTY_NOTICES.md)。
