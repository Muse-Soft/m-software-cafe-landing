# Thiết kế landing page quán cà phê — TEC-17

Nguồn yêu cầu: MSR-2 / TEC-14 (yêu cầu kiểm thử nội bộ của đội QA M-Software).
Trang tĩnh, một trang duy nhất. Bản thiết kế này đủ để Dev dựng trang (TEC-18).

> ⚠️ LƯU Ý PLACEHOLDER: MSR-2 không ghi tên quán, địa chỉ, số điện thoại hay giá món thật.
> Mọi chỗ chưa có thông tin thật đều đánh dấu **[CẦN PO BỔ SUNG]** — Dev dựng trang bằng
> placeholder này, KHÔNG tự bịa thông tin thật. Khi PO bổ sung, chỉ cần thay đúng các dòng
> đánh dấu, không đổi bố cục.

## Bố cục tổng thể (thứ tự khối, từ trên xuống dưới)

1. Hero (phần mở đầu) — toàn chiều rộng, chiều cao khoảng 1 màn hình trên desktop
2. Thực đơn ngắn (5 món)
3. Địa chỉ + giờ mở cửa
4. Nút gọi điện (khối kêu gọi hành động cuối trang) + chân trang nhỏ

Layout: mobile-first, một cột trên điện thoại; desktop tối đa 2 cột ở khối thực đơn
(2 món/cột, món thứ 5 tràn hàng cuối) và khối địa chỉ/giờ mở cửa chia 2 cột.
Không dùng framework nặng: HTML + CSS thuần là đủ cho trang tĩnh này.

---

## (a) Khối Hero — phần mở đầu

- **Tên quán:** [CẦN PO BỔ SUNG] (hiển thị lớn, căn giữa, là tiêu đề H1 duy nhất của trang)
- **Slogan:** [CẦN PO BỔ SUNG] — ví dụ dạng placeholder: "Cà phê ngon, không gian yên tĩnh"
  (dòng này chỉ là gợi ý tông giọng, PO duyệt/chốt câu thật trước khi đăng).
- **Ảnh chính:** ảnh placeholder toàn chiều rộng phía dưới tên quán + slogan.
  Mô tả ảnh cần dùng: một ly cà phê trên bàn gỗ trong không gian quán sáng, ấm.
  Ghi rõ: ảnh hiện tại là placeholder (dùng ảnh stock/mẫu), thay bằng ảnh thật của quán
  khi PO cung cấp — không dùng ảnh của quán khác.
- **Nút phụ trong hero:** nút "Xem thực đơn" cuộn xuống khối thực đơn (neo `#menu`).
  Nút gọi điện chính đặt ở khối (d) cuối trang, không nhồi thêm nút gọi ở hero để tránh
  2 nút hành động cạnh tranh nhau trên một màn hình.

## (b) Khối thực đơn — 5 món

Tiêu đề khối: "Thực đơn" (H2). Mỗi món gồm: tên món, mô tả 1 dòng, giá.
Giá dưới đây là placeholder — [CẦN PO BỔ SUNG] giá thật cho cả 5 món.

| # | Tên món | Mô tả ngắn | Giá |
|---|---------|------------|-----|
| 1 | Cà phê sữa đá | Cà phê phin đậm, sữa đặc, đá — món đặc trưng của quán | [CẦN PO BỔ SUNG] |
| 2 | Cà phê đen đá | Cà phê phin nguyên chất, ít đường, vị đậm | [CẦN PO BỔ SUNG] |
| 3 | Bạc xỉu | Nhiều sữa, ít cà phê, ngọt nhẹ, hợp người mới uống | [CẦN PO BỔ SUNG] |
| 4 | Trà đào cam sả | Trà đào mát, cam tươi, sả thơm — món không cà phê | [CẦN PO BỔ SUNG] |
| 5 | Bánh croissant | Bánh nướng giòn, ăn kèm cà phê buổi sáng | [CẦN PO BỔ SUNG] |

Trình bày: danh sách dọc, mỗi món một hàng (tên trái, giá phải, mô tả nhỏ bên dưới tên).
Desktop: chia 2 cột, món 5 ở hàng cuối. Không cần ảnh từng món ở bản đầu tiên.

## (c) Khối địa chỉ + giờ mở cửa

Tiêu đề khối: "Tìm chúng tôi" (H2). Hai cột trên desktop, xếp dọc trên mobile.

- **Địa chỉ:** [CẦN PO BỔ SUNG]
  (Khi có địa chỉ thật: hiển thị kèm link "Chỉ đường" mở Google Maps.)
- **Giờ mở cửa:** [CẦN PO BỔ SUNG]
  (Dạng cần bổ sung: ví dụ "Thứ 2 – Chủ nhật: 7:00 – 22:00" — hiện để trống, không đoán.)

## (d) Khối nút gọi điện

- **Vị trí:** cuối trang, sau khối địa chỉ/giờ mở cửa, trước chân trang. Một khối riêng,
  nền nổi bật hơn phần còn lại, căn giữa.
- **Nhãn nút:** "📞 Gọi đặt bàn / đặt món" — nút duy nhất gọi hành động chính của trang.
- **Hành vi:** bấm nút → mở trình gọi điện với số [CẦN PO BỔ SUNG] (kỹ thuật: link `tel:`).
  Khi chưa có số thật, nút hiển thị nhưng Dev để số placeholder và ghi chú rõ trong code
  là chưa có số thật — không gắn số điện thoại giả mạo có thể gọi nhầm sang người khác.
- **Chân trang (nhỏ, dưới nút):** tên quán [CẦN PO BỔ SUNG] + giờ mở cửa tóm tắt
  [CẦN PO BỔ SUNG]. Không thêm link mạng xã hội vì MSR-2 không yêu cầu.

## Checklist bàn giao cho Dev (TEC-18)

- [x] Đủ 4 khối theo thứ tự: hero → thực đơn 5 món → địa chỉ + giờ mở cửa → nút gọi điện
- [x] Placeholder nào cũng gắn cờ [CẦN PO BỔ SUNG] — không có thông tin thật nào bị bịa ra
- [ ] Dev dựng trang theo đúng thứ tự khối và layout mobile-first nêu trên
- [ ] Sau khi PO bổ sung tên/địa chỉ/số/giờ/giá: thay đúng các dòng có cờ, không đổi bố cục
