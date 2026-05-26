# ESP32-S3 Release 2026-05-26

适用板型：`ESP32-S3-N16R8`

## 文件说明

- `esp32s3-merged-16mb-20260526.bin`
  全量单文件包，包含 bootloader、分区表、OTA 数据、应用固件和 `SPIFFS` 网页资源。
- `esp32s3-ota-firmware-20260526.bin`
  应用 OTA 包，只更新程序本体，不更新网页资源。
- `esp32s3-spiffs-storage-20260526.bin`
  网页资源 OTA 包，只更新 `storage / SPIFFS` 分区，不更新程序本体。

## 什么时候用哪个

- 第一次升级到“支持网页资源 OTA”的版本：
  直接刷 `esp32s3-merged-16mb-20260526.bin` 最省事。
- 以后只改 C 代码、后端逻辑、AirPlay 行为：
  用 `esp32s3-ota-firmware-20260526.bin`
- 以后只改 `data/www/` 里的门户页面、日志页、EQ 页面等静态资源：
  在新网页里的“网页资源更新”入口上传
  `esp32s3-spiffs-storage-20260526.bin`

## 注意

- `spiffs` 资源包必须来自同一板型和同一分区方案。
- 如果网页和程序都改了，最稳的是重新刷 `merged` 全量包。
