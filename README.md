# docker

## 簡介
本專案提供一個 Docker 容器化環境，內含必要的設定檔和腳本，幫助用戶快速啟動並運行專案。請遵循以下步驟來設置和使用。

## 下載專案
使用 Git 將專案克隆到本地工作區：

```bash
git clone <你的Git倉庫URL>
cd <專案目錄名稱>
```

## 檔案權限設定
為確保腳本可執行，請執行以下命令：

```bash
chmod +x build.sh
chmod +x run.sh
```

## 構建 Docker 映像
使用提供的 Dockerfile 來構建 Docker 映像。默認情況下，映像名稱為 `custom_image`，但你可以在構建時指定自定義名稱。

### 建立 Docker 映像
執行以下命令來構建映像：

```bash
./build.sh
```

### 自定義映像名稱
如果需要修改映像名稱，請編輯 `build.sh`，找到以下行並替換：

```bash
IMAGE_NAME="custom_image"  # 修改 custom_image 為你希望的名稱
```

## 運行容器
運行腳本會啟動容器，默認容器名稱為 `custom_container`。可以通過以下命令啟動：

```bash
./run.sh
```

如需修改容器名稱或其他配置，請編輯 `run.sh`，找到以下行並替換：

```bash
CONTAINER_NAME="custom_container"  # 修改 custom_container 為你希望的名稱
```

## 修改設定檔
項目內提供了 `tmux.conf`，此檔案包含以下設定：

- 啟用滑鼠模式：`set -g mouse on`
- 快捷鍵分割窗格：
  - Ctrl+H 水平分割：`bind -n C-h split-window -h`
  - Ctrl+V 垂直分割：`bind -n C-v split-window -v`

如需自定義，可以直接修改 `tmux.conf` 文件並重啟 tmux 來應用更改。

## 附錄

### 檢查運行中的容器
使用以下命令檢查是否有運行中的容器：

```bash
docker ps
```

### 停止容器
使用以下命令停止運行中的容器：

```bash
docker stop <容器名稱>
```

### 刪除容器
如需刪除容器：

```bash
docker rm <容器名稱>
```

### 刪除映像
刪除映像可以通過以下命令：

```bash
docker rmi <映像名稱>
```
