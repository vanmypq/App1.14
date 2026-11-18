BUILD: Mở thư mục AutoAnswer bằng Android Studio, chờ Gradle sync, nối điện thoại Android 10+ (bật USB debugging), bấm Run.
Hoặc đẩy lên GitHub: Actions > Build APK > tải app-debug.apk.
SỬ DỤNG: Mở app > nhập API key > Lưu > (Cấp quyền chụp màn hình) > Bật dịch vụ Trợ năng > mở app/web có câu trắc nghiệm > bấm nút nổi "▶ AI".
v1.1: tự nhận mọi dạng (A/B/C/D, chỉ có ô tích chọn, nhiều đáp án đúng, Đúng/Sai, nhiều câu cùng màn hình); chế độ NHANH (mặc định, không suy nghĩ, không giải thích, chạm ngay).
Android 10: chỉ đọc được chữ qua cây giao diện. Không có OCR ảnh (cần Android 11+).
Nếu Android chặn ("Restricted setting"): Cài đặt > Ứng dụng > Auto Trắc Nghiệm > ⋮ > Cho phép cài đặt bị hạn chế.
v1.9: CUỘN TRANG + QUA TRANG.
  - Tự cuộn: làm xong các câu đang hiện -> tự cuộn xuống; cuộn không đổi nội dung nữa = đã hết trang.
  - Tự qua trang: hết trang -> tự bấm nút "Tiếp theo / Tiếp tục / Câu sau / Trang sau / Next / Continue / ›".
    Không có nút: bật tuỳ chọn "vuốt ngang" để vuốt sang trang. "Nộp bài/Kết thúc" chỉ bấm khi bạn bật riêng.
  - Hết câu hoặc nút không đổi được trang (2 lần) -> tự dừng và báo "✔ đã làm hết".
  - Tuỳ chọn bật/tắt từng tính năng nằm trong màn hình chính của app.
v1.9.1: sửa lỗi chỉ làm 1-2 câu đầu rồi dừng trong danh sách dài.
  - Cuộn thử 3 cách (lệnh cuộn Trợ năng, vuốt giữa, vuốt lệch) và CHỈ kết luận "hết trang" khi nội dung thật sự không đổi 2 lần liên tiếp.
  - Nhấn giữ nút nổi ▶ AI để sao chép dữ liệu, có thêm "NHẬT KÝ CUỘN" để chẩn đoán nếu vẫn không cuộn được.
v1.9.2: sửa lỗi trang web nhiều câu trắc nghiệm (Chrome, file HTML) - AI trả rỗng, không cuộn được.
  - Ô chọn không có chữ: lấy nhãn từ cây giao diện; nếu không có thì đặt tên A/B/C/D theo thứ tự dưới mỗi câu để AI nhìn ảnh rồi chọn.
  - Không còn gắn nhầm tiêu đề "BÀI KIỂM TRA..." làm nhãn cho mọi ô.
  - Bỏ chữ của câu nằm ngoài màn hình (trình duyệt liệt kê cả phần chưa cuộn tới) và dùng đúng vị trí chữ.
  - Chữ thường bị ẩn gọi là "(chữ ẩn)", không còn bị coi là công thức.
  - Nhận biết đã cuộn được bằng vị trí nội dung, không chỉ bằng chữ.
v1.9.3: ẢNH LÀ NGUỒN CHÍNH + rà soát tốc độ/độ chính xác.
  - Luôn gửi ảnh chụp màn hình cho AI (có thể tắt trong màn hình chính: "Luôn gửi ảnh chụp..."). Lời nhắc dặn AI đọc câu hỏi/phương án TRỰC TIẾP trong ảnh.
  - Mỗi ô chọn/ô nhập gửi kèm vị trí {x% y%} để AI đối chiếu ô với phương án trong ảnh rồi trả đúng [id] để app chạm.
  - Chụp ảnh: luôn dùng KHUNG HÌNH MỚI NHẤT (không còn nguy cơ gửi ảnh cũ), độ phân giải cao hơn (1600px, chế độ nhanh 1280px).
  - Phát hiện ảnh bị đen (app chặn chụp màn hình) và báo, tự dùng chữ thay thế.
  - Nút radio chưa được tích sau khi chạm: tự bấm lại 1 lần.
  - Thời gian chờ mạng dài hơn khi gửi ảnh (đỡ bị chuyển sang model Lite), tự thử lại model tốt nhất sau 2 phút.
v1.9.4: CHẾ ĐỘ NHÌN ẢNH (trang web không đưa nội dung câu hỏi/ô chọn cho Trợ năng).
  - Khi cây giao diện chỉ có vỏ trình duyệt (không có ô chọn), hoặc AI trả rỗng ở lần đầu: gửi ảnh chụp, AI đọc câu hỏi,
    chọn đáp án và trả TOẠ ĐỘ ô cần chạm (chuẩn hoá 0..1000); app chạm đúng toạ độ đó trên màn hình bài tập.
  - Nhận biết màn hình đã cuộn/đổi bằng HÌNH ẢNH (lưới 24x48), nên cuộn trang web hoạt động đúng; chờ trang đứng yên mới hỏi AI.
  - Câu bị cắt ở mép màn hình hoặc đã tích: AI bỏ qua; cuộn xuống rồi làm tiếp.
  - Nhấn giữ nút nổi: kèm lý do khi app phải chuyển từ model Flash sang Flash-Lite.
v1.9.5: CUỘN THEO CÂU + TĂNG TỐC.
  - AI chỉ trả lời câu hiện ĐỦ đề và ĐỦ phương án; câu bị cắt ở mép màn hình thì AI báo mức cần kéo ("cuon"), app kéo trang
    CHÍNH XÁC đoạn đó (kéo rồi giữ yên để không trượt thêm) cho đầu câu kế tiếp lên sát mép trên, rồi mới đọc và trả lời.
  - Trang đọc được bằng cây giao diện: tự ước tính mức kéo từ vị trí dòng tiêu đề câu cuối.
  - Chống lặp lên-xuống khi câu dài hơn cả màn hình.
  - Tốc độ: ảnh gửi AI nhỏ hơn (1024px, chế độ Nhanh), AI không "suy nghĩ dài" ở chế độ Nhanh, chạm cách nhau 50ms,
    cuộn ngay sau khi chạm, kiểm tra màn hình đổi mỗi 100ms thay vì chờ cố định.
v1.9.6: SỬA "LÚC NHẬN ĐƯỢC CÂU, LÚC KHÔNG" + HẾT HẠN MỨC API.
  Nguyên nhân tìm thấy trong log:
  1) HTTP 429 (hết hạn mức) làm app xoay vòng model lung tung, sau 2 phút lại thử lại model đã hết quota -> lúc được lúc không.
     Sửa: khoá riêng từng (key, model) theo thời gian server yêu cầu chờ (retryDelay); hết quota theo ngày thì khoá 1 giờ.
     Có thể dán NHIỀU API key cách nhau dấu phẩy: key nào hết quota thì tự chuyển sang key khác.
  2) AI ghi sai toạ độ (đáp án 2 nhưng toạ độ rơi vào phương án 3).
     Sửa: AI phải liệt kê toạ độ TỪNG phương án của câu; app lấy toạ độ của chính phương án được chọn, kiểm tra y tăng dần,
     không hợp lệ thì nhìn lại thay vì chạm bừa.
  3) Chế độ nhìn ảnh lúc bật lúc tắt do tiêu chí đếm chữ dài (tiêu đề trang/URL dài). Sửa: không có ô chọn trong cây giao diện = luôn nhìn ảnh.
  4) App kết luận "đã làm hết" quá sớm. Sửa: AI báo từng câu (đủ/thiếu, đã chọn/chưa, vị trí đầu-cuối); app tự tính mức kéo trang
     để câu chưa làm lên sát mép trên; còn câu chưa làm thì chưa kết thúc (thử lại tối đa 3 lần).
v1.9.7: SỬA "AI LUÔN KHÔNG CHỌN ĐƯỢC CÂU NÀY" (câu bị bỏ qua, cuộn 800 liên tục).
  Nguyên nhân (từ log): model Lite (do Flash hết hạn mức 429) báo sai dc=true ("câu đã chọn") cho câu CHƯA chọn, app tin nên bỏ qua
  rồi coi mọi câu đã xong và cuộn 800 mỗi lần -> lướt qua mà không làm câu nào.
  Sửa:
  - App tự kiểm tra ô đã chọn bằng ĐIỂM ẢNH tại từng ô tròn (CaptureService.isSelectedAt), không tin cờ dc của AI.
  - "Câu hiện đủ" tính từ toạ độ AI đo (có tiêu đề + phương án cuối trong ảnh), không tin cờ dd.
  - Câu đủ, chưa chọn mà AI không trả đáp án -> nhìn lại kèm gợi ý "câu N đã hiện trọn và chưa được chọn".
  - Sau khi chạm kiểm tra lại ô đã tích chưa; chưa thì bấm lại 1 lần vào chữ của phương án.
  - Chỉ kéo ngược lên tối đa 2 lần mỗi lượt chạy (đã có đầu câu bị cắt ở mép trên là câu đã xử lý ở màn hình trước).
v1.9.8: SỬA CHỌN NHẦM ĐÁP ÁN + LÀM LẠI CÂU BỊ CHẤM SAI.
  Nguyên nhân (từ log): ở chế độ chữ, AI hiểu đúng đáp án câu 2 ("Giáo viên điều chỉnh nội dung...") nhưng ô chọn của phương án đó
  nằm NGOÀI màn hình nên không có trong danh sách; AI gắn nhầm vào [17] (ô của phương án đầu tiên) -> chọn sai, trang báo
  "Bạn đã trả lời sai, vui lòng làm lại". Ngoài ra cây giao diện luôn báo ô ☐ (không phản ánh ô đã chọn).
  Sửa:
  - ẢNH LÀ NGUỒN CHÍNH: mọi màn hình trắc nghiệm đều dùng chế độ nhìn ảnh (chỉ dùng chế độ chữ khi có ô nhập chữ trong vùng trang).
    Câu chỉ được làm khi hiện ĐỦ đề và ĐỦ phương án (theo toạ độ), tránh gắn nhầm ô.
  - Nhận biết ô ĐỎ (chọn sai) bằng điểm ảnh: coi là chưa xong, nhìn lại ngay, chọn phương án KHÁC (tối đa 3 lần/màn hình).
  - Sau khi chạm: nếu ô vừa chọn bị chấm đỏ thì chưa cuộn đi mà chọn lại.
v1.9.10: THEO DÕI KHI NGƯỜI DÙNG TỰ CUỘN + CUỘN THEO ĐÁP ÁN CUỐI + PHẢN HỒI NHANH (nhất là câu đầu tiên).
  1) Chế độ "Tôi tự cuộn trang" (tuỳ chọn mới ở màn hình chính): app KHÔNG tự cuộn/qua trang. Bạn cuộn tới đâu, dừng lại là app đọc ảnh
     và chạm đáp án các câu đang hiện đủ (không chờ cố định: màn hình đứng yên là xử lý ngay).
     Khi màn hình đang trôi, app chỉ so sánh ảnh rất nhẹ (không đọc cây giao diện) nên không tốn công.
  2) Cuộn tự động: khi mọi câu đang hiện đã làm xong, kéo xuống ĐÚNG vị trí phương án cuối của câu thấp nhất (đưa nó lên sát mép trên)
     để câu kế tiếp hiện ngay bên dưới, trọn vẹn nhất. Có bù đoạn ngón tay trượt đầu tiên (touch slop).
  3) Phản hồi nhanh:
     - AI trả lời định dạng GỌN (mỗi câu ~40 ký tự thay vì ~150, bỏ cờ dd và lời giải thích ở chế độ Nhanh) -> ít chữ phải sinh ra hơn.
     - Chế độ Nhanh ưu tiên model Lite (nhanh hơn, hạn mức/phút cao hơn); ảnh 960px chất lượng 55 nhẹ hơn.
     - Câu ĐẦU TIÊN: khi bật AI, ảnh đã được mã hoá sẵn, kết nối mạng đã mở sẵn ở luồng riêng (không xếp hàng sau lượt hỏi), màn hình
       hiện tại được coi là đã đứng yên nên không chờ ổn định; vòng quét 100ms.
  Lưu ý: chế độ Nhanh bỏ phần suy luận nên có thể sai ở câu khó; muốn chính xác hơn thì tắt "Nhanh".
v1.9.11: cuộn sau khi làm xong: đưa phương án cuối của câu thấp nhất lên khoảng 1/4 chiều cao từ mép trên (ANCHOR_Y = 250) thay vì sát mép trên;
  câu kế tiếp hiện ngay bên dưới và vẫn còn thấy phần cuối câu trước để đối chiếu.
v1.9.12: ANCHOR_Y đổi 250 -> 350: sau khi làm xong, phương án cuối của câu thấp nhất được đưa lên khoảng 35% chiều cao từ mép trên (thấp hơn bản 1.9.11).
v1.9.13: LỆNH CUỘN TRANG: mỗi lần kéo luôn bắt đầu từ GIỮA màn hình và kéo ngón tay lên tới sát mép trên (cuộn lên thì từ giữa kéo xuống).
  Một lần kéo tối đa ~46% chiều cao; cần cuộn nhiều hơn thì kéo liên tiếp nhiều lần, mỗi lần lại bắt đầu từ giữa (giữ yên cuối mỗi lần để trang không trượt thêm).
  Vuốt dự phòng cũng bắt đầu từ giữa màn hình.
v1.9.14: THÊM DẠNG TRẮC NGHIỆM "THẺ" (mỗi phương án là thẻ bo tròn có huy hiệu chữ cái A/B/C/D, không có ô tròn rỗng).
  - AI báo thêm cờ "the" (true = dạng thẻ); x/ys là tâm huy hiệu chữ cái. Câu không có số thứ tự vẫn nhận (đề bài là tiêu đề).
  - Nhận biết thẻ đã chọn bằng điểm ảnh: so màu huy hiệu, nền thẻ và VIỀN thẻ giữa các phương án cùng câu (phương án nào đổi màu
    rõ rệt = đã chọn; đỏ = chọn sai -> chọn lại; xanh lá = đúng). Không đọc điểm ngay giữa huy hiệu nữa (trúng nét chữ -> báo nhầm "đã chọn").
  - Kiểm tra sau khi chạm + bấm lại vào chữ phương án nếu chưa trúng, dùng cùng cách so màu này.
  - Nút qua trang nhận thêm: Kiểm tra / Xác nhận / Check / Confirm.
  - Dạng ô tròn/radio cũ vẫn chạy như 1.9.13 (the=false).
v1.9.15: TĂNG TỐC + CHÍNH XÁC HƠN.
  - Chế độ nhìn ảnh luôn ưu tiên model Flash đầy đủ (Lite chỉ là dự phòng); AI ghi lý do/phép tính cực ngắn ("tinh") TRƯỚC khi chọn, kể cả chế độ Nhanh.
  - Ảnh chế độ Nhanh 1100px (chữ có dấu rõ hơn). Chọn sai (thẻ/ô đỏ) được chọn lại tới 3 lần mỗi câu, tối đa 60 lần mỗi lượt chạy (trước là 12).
  - Bớt thời gian chờ cố định: vòng quét 70ms, chờ yên màn hình 150ms, kiểm tra sau chạm 180ms, nhịp kiểm tra cuộn 60ms.
