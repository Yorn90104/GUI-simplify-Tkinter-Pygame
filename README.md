# 視窗和音頻框架

本項目實現了一個基於 Python 的 GUI 和音頻處理框架，使用 `Tkinter` 作為圖形界面庫，並使用 `pygame.mixer` 處理音頻播放。該框架包括用於管理視窗、圖像和音頻資源的類，為構建具有交互功能的應用程序提供了多種工具。

## 功能

### 1. **視窗管理 (`Window` 類)**
- **固定大小的 GUI**：創建一個固定大小的 GUI 視窗（默認不可調整大小）。
- **畫布和框架**：支持多個畫布和框架，靈活進行佈局管理。
- **按鈕和輸入框**：
  - 支持圖片按鈕和文字按鈕。
  - 支持動態內容處理的輸入框。
- **臨時文件管理**：
  - 處理臨時文件（如圖標和音頻）。
  - 在程序退出時清理臨時文件。

### 2. **圖片處理 (`Picture` 類)**
- 將 Base64 編碼的圖片轉換為 `ImageTk.PhotoImage` 對象。
- 使用高質量縮放動態調整圖片大小。

### 3. **音頻管理 (`Audio` 類)**
- **音樂播放**：
  - 支持背景音樂播放，音量控制和循環播放。
  - 動態切換不同的音樂曲目。
- **音效播放**：
  - 支持播放單個音效，並可調節音量。
- **Base64 音頻解碼**：
  - 將 Base64 編碼的 WAV 文件解碼為可播放的音樂和音效。
  - 使用臨時文件管理磁盤佔用。

## 快速開始

### 環境需求
- Python 3.8+
- 必需庫：
  - `tkinter`（標準庫，用於 GUI 開發）
  - `Pillow` 用於圖像處理
  - `pygame` 用於音頻播放

### 安裝
1. 克隆此倉庫：
   ```bash
   git clone https://github.com/Yorn90104/GUI-simplify-Tkinter-Pygame-.git
   ```
2. 安裝依賴項：
   ```bash
   pip install pygame pillow
   ```

### 使用方法

#### 初始化示例
以下是初始化 `Window` 類並設置基本 GUI 的示例：

```python
from your_module import Window, Picture, Audio

# 初始化主窗口
app = Window(title="示例應用程序", width=800, height=600)

# 添加框架和畫布
app.setup_frame_and_canvas("主畫面")
app.first_window("主畫面")

# 運行應用程序
app.mainloop()
```

#### 播放音頻
```python
audio = Audio()
audio.decode_music(base64_music_dict, "背景音樂")
audio.play_music("背景音樂", volume=0.5)
```

#### 添加圖片按鈕
```python
image_button_img = Picture.process_image_base64(image_dict, "按鈕圖片", width=100, height=50)
app.image_button("開始按鈕", CMD=lambda: print("按鈕被點擊"), canvas_name="主畫面", img=image_button_img, x=200, y=300)
```

## 結構
- `Window`：管理 GUI 組件，例如按鈕、畫布和框架。
- `Picture`：處理 Base64 圖片的解碼和處理。
- `Audio`：提供音樂和音效管理，包括解碼 Base64 音頻。

## 未來改進
- **動態視窗調整**：添加支持動態佈局調整的功能。
- **多語言支持**：整合翻譯系統以支持多語言應用程序。
- **增強音頻格式支持**：擴展對 MP3 和其他音頻格式的支持。

## 授權
本項目基於 MIT 許可證進行授權。詳情請參閱 `LICENSE` 文件。

## 致謝
- `Tkinter`：Python 的標準 GUI 工具包。
- `Pillow`：用於圖像處理的 Python 庫。
- `pygame`：用於音頻處理的 Python 遊戲庫。

---

# Window and Audio Framework

This project implements a Python-based GUI and audio processing framework using the `Tkinter` library for graphical interfaces and `pygame.mixer` for audio playback. It includes classes for managing windows, images, and audio resources, providing a versatile toolset for building applications with interactive features.

## Features

### 1. **Window Management (`Window` Class)**
- **Resizable GUI**: Creates a fixed-size GUI window (non-resizable by default).
- **Canvas and Frames**: Supports multiple canvases and frames for flexible layout management.
- **Buttons and Input Boxes**:
  - Image buttons and text buttons.
  - Input boxes with dynamic content handling.
- **Temporary File Management**:
  - Handles temporary files such as icons and audio.
  - Cleans up temporary files upon program exit.

### 2. **Image Handling (`Picture` Class)**
- Processes base64-encoded images into `ImageTk.PhotoImage` objects.
- Supports dynamic resizing of images using high-quality scaling.

### 3. **Audio Management (`Audio` Class)**
- **Music Playback**:
  - Background music with volume control and looping options.
  - Switching between different music tracks dynamically.
- **Sound Effects**:
  - Plays individual sound effects with adjustable volume.
- **Base64 Audio Decoding**:
  - Decodes base64-encoded WAV files for sound and music playback.
  - Manages temporary audio files to minimize disk usage.

## Getting Started

### Prerequisites
- Python 3.8+
- Required libraries:
  - `tkinter` (standard library for GUI development)
  - `Pillow` for image processing
  - `pygame` for audio playback

### Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/your-repository-url
   cd your-repository
   ```
2. Install dependencies:
   ```bash
   pip install pygame pillow
   ```

### Usage

#### Example Initialization
Here is an example of initializing the `Window` class and setting up a basic GUI:

```python
from your_module import Window, Picture, Audio

# Initialize the main window
app = Window(title="Demo Application", width=800, height=600)

# Add frames and canvases
app.setup_frame_and_canvas("MainScreen")
app.first_window("MainScreen")

# Run the application
app.mainloop()
```

#### Playing Audio
```python
audio = Audio()
audio.decode_music(base64_music_dict, "background_music")
audio.play_music("background_music", volume=0.5)
```

#### Adding Image Buttons
```python
image_button_img = Picture.process_image_base64(image_dict, "button_image", width=100, height=50)
app.image_button("start_button", CMD=lambda: print("Button Pressed"), canvas_name="MainScreen", img=image_button_img, x=200, y=300)
```

## Structure
- `Window`: Manages GUI components like buttons, canvases, and frames.
- `Picture`: Handles base64 image decoding and processing.
- `Audio`: Provides music and sound effect management, including decoding base64 audio.

## Future Improvements
- **Dynamic Window Resizing**: Add support for dynamic layout adjustments when resizing.
- **Multi-language Support**: Integrate a translation system for multilingual applications.
- **Enhanced Audio Formats**: Expand support to include MP3 and other audio formats.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

## Acknowledgments
- `Tkinter`: Python's standard GUI toolkit.
- `Pillow`: Python Imaging Library for image processing.
- `pygame`: Python game library for handling audio.

