# Tizen / webOS Minimal - Compose for TV - 1 Click APK

## CÁCH CÓ APK KHÔNG CẦN ANDROID STUDIO (Khuyên dùng)

### Cách 1: Dùng GitHub Actions - 1 Click, không cài gì (2 phút)

1. Tạo repo mới trên GitHub.com (đặt tên tizen-launcher)
2. Upload toàn bộ file trong thư mục này lên repo (kéo thả là xong)
3. Vào tab **Actions** trên GitHub -> bạn sẽ thấy workflow **Build Tizen TV Launcher APK** đang chạy
4. Đợi 2-3 phút xong -> vào **Artifacts** -> tải file **TizenLauncher-debug-apk.zip**
5. Giải nén ra được **app-debug.apk** -> copy vào USB -> cài lên TV là xong!

=> Không cần cài Android Studio, không cần cài SDK, GitHub build dùm.

### Cách 2: Dùng Docker (nếu có Docker Desktop)

Chạy lệnh này trong thư mục project:

```
docker run --rm -v "$PWD":/project -w /project mingc/android-build-box bash -c "./gradlew assembleDebug"
```

APK sẽ nằm ở app/build/outputs/apk/debug/

### Cách 3: Dùng Android Studio (truyền thống)

Mở project > Build > Build APK(s)

---

## File chính bạn hỏi:

- `app/build.gradle.kts` : đã dùng `androidx.tv:tv-material:1.0.1` + `tv-foundation:1.0.1` - mới nhất của Google 2025-2026
- `MainActivity.kt` : 100% Compose for TV, style Tizen/webOS minimal (card bo 18dp, focus scale 1.05 + viền trắng 2dp)

## Cài lên TV:

1. Bật Developer Options trên TV: Settings > About > Click 7 lần vào Build
2. Bật Install from Unknown Sources
3. Dùng app Send Files to TV để gửi APK từ điện thoại lên TV
4. Cài xong, TV sẽ hỏi đặt làm Home mặc định -> chọn Tizen Launcher

Skill: Design UX/UI Launcher - Tizen/webOS Minimal
