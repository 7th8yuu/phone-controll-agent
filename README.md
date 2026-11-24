# AIRI Android APK builder

Repo này chỉ chứa một workflow GitHub Actions. Nó tải mã nguồn công khai của [moeru-ai/airi](https://github.com/moeru-ai/airi), build bản Android thử nghiệm (Stage Pocket, Capacitor) và đưa file APK debug lên **Releases**.

> Đây là bản build không chính thức, chưa chắc chạy ổn. Stage Pocket vẫn đang ở giai đoạn phát triển sớm.

## Lấy APK

1. Vào tab **Actions**, chọn **Build AIRI APK**. Workflow tự chạy mỗi lần push vào `main`, hoặc bấm **Run workflow** để chạy lại (có thể điền nhánh, tag hoặc commit của airi ở ô `ref`).
2. Chờ build xong (khoảng 10 đến 25 phút).
3. Vào **Releases**, mở bản **AIRI Android (debug build)**, tải `AIRI.apk` rồi cài. Nếu máy hỏi thì cho phép cài từ nguồn không rõ.

APK cũng nằm ở mục Artifacts của lần chạy workflow.

## Ghi chú

- Workflow dùng đúng phiên bản Node và pnpm mà airi ghim trong `.tool-versions`.
- Nếu airi chưa có thư mục `android/`, workflow tự tạo bằng `cap add android`.
- APK này là bản debug, tự ký bằng khoá debug. Không dùng để đưa lên Google Play.
- Để dùng được, bạn vẫn cần cấu hình nhà cung cấp model và API key trong phần Settings của AIRI.
