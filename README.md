# AutoCAD AI Studio

**Ứng dụng Windows** kết nối **Google Gemini AI** với **AutoCAD**: vẽ bằng ngôn ngữ tự nhiên, quét bản vẽ / DXF, dự toán BOM và xuất Excel. Bản quyền freemium **FREE / PRO / VIP**.

![AutoCAD AI Studio](packaging/icons/app.png)

---

## Tính năng chính

| Tab | FREE | PRO / VIP |
|-----|------|-----------|
| **AI Drawing** — prompt tiếng Việt/Anh → AutoLISP → gửi vào AutoCAD | Có (cần Gemini key + AutoCAD) | Có |
| **BOM Estimator** — mở DXF / scan live AutoCAD → bảng khối lượng | Mở DXF, scan, export có watermark | **Estimate AI** + Excel đầy đủ |
| **Settings & License** — HWID, kích hoạt key, Gemini API key | Có | Có |

- Đồng bộ cài đặt mới lên Google Sheets + thông báo Telegram (admin).
- License online qua key `PRO-…` / `VIP-…`, hoặc blob RSA offline (tuỳ cấu hình).

---

## Yêu cầu hệ thống

- **Windows 10 / 11** (x64)
- **Microsoft Visual C++ 2015–2022 x64** (Setup có thể cài kèm nếu builder đóng gói `vc_redist`)
- **AutoCAD** (bản đăng ký COM `AutoCAD.Application`) — để Drawing / Scan live
- **Kết nối Internet** — Gemini API + kích hoạt / đồng bộ license
- **Google Gemini API key** — [tạo tại Google AI Studio](https://aistudio.google.com/apikey)

> Không cần cài Python. Khách chỉ chạy file Setup hoặc exe portable.

---

## Cài đặt (khách hàng)

### Cách 1 — Setup (khuyên dùng)

1. Tải **`AutoCAD_AI_Studio_Setup_1.0.2.exe`** từ [Releases](https://github.com/ntdphi004/AutoCAD-AI-Studio-Release/releases).
2. Chạy Setup → Next → cài vào `C:\Program Files\AutoCAD AI Studio` (hoặc thư mục bạn chọn).
3. Tùy chọn tạo shortcut Desktop.
4. Mở **AutoCAD AI Studio** từ Start Menu.

### Cách 2 — Portable

1. Tải **`AutoCAD_AI_Studio.exe`**.
2. Đặt vào thư mục bất kỳ (không cần cài).
3. Double-click để chạy.

### Lần chạy đầu

1. App mở ngay với gói **FREE** (không bắt buộc nhập key).
2. Có thể hiện Welcome — đọc nhanh rồi đóng.
3. Vào tab **Settings & License**:
   - Dán **Gemini API key** → **Save Key** (lưu tại `%LOCALAPPDATA%\AutoCAD_AI_Studio\settings.env`).
   - Sao chép **Machine Code (HWID)** nếu cần nâng cấp PRO/VIP.
4. Mở **AutoCAD** và tạo/mở ít nhất **một file DWG** trước khi dùng Drawing hoặc Scan live.

Nếu thiếu VC++ Runtime, Windows sẽ báo lỗi khi mở app — cài [VC++ x64](https://aka.ms/vs/17/release/vc_redist.x64.exe) rồi chạy lại.

---

## Hướng dẫn sử dụng

### 1. AI Drawing (vẽ bằng prompt)

1. Mở AutoCAD + một bản vẽ.
2. Tab **AI Drawing Assistant**.
3. Kiểm tra status: AutoCAD Ready + Gemini ready (xanh).
4. Nhập prompt, ví dụ: *“Vẽ hình chữ nhật 2000×1000 mm từ gốc tọa độ”*.
5. Bấm **Generate & Send to AutoCAD** (hoặc Quick Draw).
6. Xem lệnh AutoLISP trong log và kết quả trên viewport AutoCAD.

**Lỗi thường gặp**

| Hiện tượng | Cách xử lý |
|------------|------------|
| AutoCAD: Not installed / Not running | Cài AutoCAD, mở chương trình, mở DWG |
| Gemini: missing key | Settings → nhập API key → Save |
| Gemini tạm thời không phản hồi (503) | Đợi 1–2 phút, thử lại |

### 2. BOM / Dự toán

1. Tab **DXF & CAD Estimator**.
2. **Open DXF** *hoặc* **Scan Live AutoCAD** (cần AutoCAD đang mở bản vẽ).
3. (PRO+) Bấm **Estimate BOM (AI)** — FREE sẽ được hướng dẫn nâng cấp.
4. Sửa số lượng / đơn giá trên bảng nếu cần.
5. **Export Excel**.

| Gói | Estimate BOM | Export |
|-----|--------------|--------|
| FREE | Khóa | Có watermark, giới hạn dòng |
| PRO / VIP | AI unlocked | Đầy đủ |

### 3. Nâng cấp PRO / VIP

1. Settings → copy **HWID**.
2. Gửi HWID tới bot hỗ trợ Telegram trong app (link Settings / Welcome).
3. Nhận key dạng `PRO-XXXXXXXX` hoặc `VIP-XXXXXXXX`.
4. Dán vào ô Upgrade key → **Activate Upgrade**.
5. Plan hiển thị **PRO** / **VIP**, nút Estimate mở khóa.

---

## Gói bản quyền (tóm tắt)

| | FREE | PRO | VIP |
|-|------|-----|-----|
| AI Drawing → AutoCAD | Có | Có | Có |
| Estimate BOM (AI) | Không | Có | Có |
| Export Excel | Watermark | Full | Full |
| Thời hạn | Vô hạn (FREE) | ~10 năm (theo cấp key) | ~12 tháng (theo cấp key) |

---

## Tải về

| File | Mô tả |
|------|--------|
| [Setup Installer](https://github.com/ntdphi004/AutoCAD-AI-Studio-Release/releases/latest) | Cài đặt chuẩn + shortcut |
| Portable `.exe` | Chạy không cần cài |

Release mới nhất: **https://github.com/ntdphi004/AutoCAD-AI-Studio-Release/releases/latest**

---

## Hỗ trợ

- Telegram hỗ trợ: xem link trong tab Settings của app  
- Báo lỗi / góp ý: mở Issue trên repo này (nếu bật) hoặc nhắn Telegram  

---

## Dành cho nhà phát triển

Mã nguồn & build pipeline nằm ở repo riêng (private). Tóm tắt build:

```powershell
cd autocad_ai_studio
copy .env.production.example .env.production
# Điền KEYS_GS_WEBAPP_URL + KEYS_GS_SERVER_SECRET
.\build_setup.ps1
```

Output: `dist\AutoCAD_AI_Studio.exe` và `dist\AutoCAD_AI_Studio_Setup_1.0.2.exe` (có icon).

Chi tiết kỹ thuật: xem `PLAN_PROMPT.md` trong source tree.

---

## Phiên bản

- **v1.0.2** — Live scan INSUNITS → meters (BOM khớp DXF); plan/docs sync
- **v1.0.1** — Telegram install-notify retry + Setup filename matches release tag
- **v1.0.0** — First public customer release (Windows x64, encrypted ship config, Setup + portable)

© AutoCAD AI Studio
