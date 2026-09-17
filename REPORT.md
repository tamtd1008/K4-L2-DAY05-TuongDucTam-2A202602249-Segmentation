# Báo cáo Day 5 — điền trực tiếp trong fork của bạn

**Cách dùng:** Thay mọi dấu `…` bằng bài làm thật của bạn trước khi nộp link fork trên VLearn. Giữ nguyên bốn mục và bảng để coach đọc nhanh. Viết ngắn, cụ thể theo ảnh/vùng; không cần thuật ngữ chuyên sâu. Ví dụ trong [hướng dẫn mẫu](reports/REPORT_TEMPLATE.md) chỉ giúp hiểu cách điền, không phải câu trả lời để chép lại.

- Mã học viên theo lớp: 2A202602249
- Ngày / CVAT local: 17/09/2026
- Công cụ đã dùng: Không có

Mã học viên là mã lớp cấp; không cần ghi họ tên trong report nếu kênh VLearn đã nhận diện bạn. Chỉ ghi công cụ thật sự đã dùng; không có SAM vẫn làm bài bình thường.

## 1. Bài đã nộp

Ghi tên ZIP đúng như file trong `submissions/` và số ảnh đã vẽ, Save. Chưa làm hoặc export lỗi thì ghi `chưa có`, không tạo ZIP rỗng. Cột điểm là điểm tối đa của task, **không phải điểm tự chấm**.

| Task | File ZIP đúng tên | Hoàn thành mấy ảnh | Điểm tối đa (coach chấm sau) |
easy_semantic      semantic  3 ảnh · 20 điểm · Segmentation mask 1.1
  ảnh: 7ee6d192-89e2408b.jpg, 817bca71-00000000.jpg, 81ae7cbb-6bc63a4a.jpg
  class: building, road, sidewalk, sky, vegetation
medium_instance    instance  3 ảnh · 32 điểm · COCO 1.0
  ảnh: 000000181542.jpg, 000000373353.jpg, 000000458325.jpg
  class: bicycle, bus, car, motorcycle, person, truck
hard_panoptic      panoptic  2 ảnh · 30 điểm · COCO 1.0
  ảnh: 000000350023.jpg, 000000460147.jpg
  class: bicycle, building, bus, car, motorcycle, person, road, sidewalk, sky, traffic light, truck, vegetation
cp1_holes          instance  1 ảnh · 3 điểm · COCO 1.0
  ảnh: 000000144300.jpg
  class: bicycle, bus, car, motorcycle, person, truck
cp2_slice          instance  1 ảnh · 3 điểm · COCO 1.0
  ảnh: 000000017627.jpg
  class: bicycle, bus, car, motorcycle, person, truck
cp5_occlusion      instance  1 ảnh · 3 điểm · COCO 1.0
  ảnh: 000000336232.jpg
  class: bicycle, bus, car, motorcycle, person, truck
cp3_thin           semantic  1 ảnh · 3 điểm · Segmentation mask 1.1
  ảnh: 839f7736-abe28069.jpg
  class: pole, road, sky, traffic sign
cp4_curb           semantic  1 ảnh · 3 điểm · Segmentation mask 1.1
  ảnh: 7d83710e-4697c3b2.jpg
  class: road, sidewalk
cp6_coverage       semantic  1 ảnh · 3 điểm · Segmentation mask 1.1
  ảnh: 7daa6479-67988f3f.jpg
  class: building, car, person, road, sidewalk, sky, vegetation
Tổng điểm tối đa: 100


Nếu export lỗi, ghi task, dữ liệu đã Save đến đâu và lỗi đã báo coach.

## 2. Một quyết định trước khi dùng gợi ý

Chọn object đầu tiên bạn tự vẽ ở `medium_instance`, trước khi xem bất kỳ đề xuất tự động nào cho object đó. Ghi ảnh/vị trí đủ để tìm lại; “quy tắc biên” là lý do bạn chọn hoặc dừng mask ở ranh đó.

- Ảnh, vị trí và object Medium đầu tiên tự vẽ: ảnh 000000181542.jpg, vị trí task #2 job #2, object BUS 1
- Class và quy tắc tôi dùng để chọn biên: class bus, quy tắc vật thể riêng lẻ, không trùng vị trí nhiều với các vật thể khác thì vẽ trước
- Nếu dùng gợi ý sau đó: vùng gợi ý sai/đúng, hành động sửa/giữ và lý do: không dùng
- Nếu không dùng gợi ý: ghi “không dùng”; vẫn giải thích một quyết định gán nhãn của mình.

## 3. Một lỗi tôi tìm thấy và sửa

Chọn một lỗi **có thật** trong bài. Nếu công cụ lỗi khiến bạn chưa sửa được, ghi rõ đã thử gì và cần coach hỗ trợ gì; không ghi “đã sửa” khi chưa sửa.

- Task/ảnh/vùng:
- Lỗi thuộc loại: sai lớp / thiếu-thừa vật / gộp-tách / biên / phủ vùng / khác: 
- Bằng chứng tôi nhìn thấy:
- Quy tắc và hành động sửa:
- Sau sửa đã Save và export lại chưa? 

Nếu bạn **đã xem Summary tự đánh giá trên GitHub Actions hoặc tự chạy script**, ghi ngắn một kết quả liên quan lỗi vừa sửa (ví dụ task, metric trước/sau nếu có): / chưa có điểm. Scorecard ba tier tối đa **82**, không phải điểm cuối trên 100. Không tự ghi PASS/top 3/bonus; người phụ trách xác nhận theo tiêu chí lớp. Không đưa file ground truth vào fork.

## 4. Ba ca chưa chắc hoặc đã cân nhắc

Mỗi ca là một **vùng cụ thể** khiến bạn phải cân nhắc hai cách hiểu. Ghi dấu hiệu nhìn thấy hoặc quy tắc đã dùng, rồi nêu quyết định hoặc câu hỏi cho coach. Không cần ba lỗi; ca đã quyết định được cũng hợp lệ.

| Ảnh/vị trí | Hai cách hiểu có thể | Quy tắc/chứng cứ | Quyết định hoặc câu hỏi cho coach |
| --- | --- | --- | --- |
| 1 | 000000181542.jpg| Car 7 bị chia đôi bởi 1 vật thể chắn phía trước, nên ghép lại thành 1 hay chia làm 2 vật thể |  |
| 2 | 000000181542.jpg | Personal 16, Personal 17 cùng ngồi chung 1 xe máy, gần nhau, chia làm 2 vật thể hay gộp chung thành 1 | |
| 3 | 000000181542.jpg | Mortocycle 2 chỉ lộ 1 phần nhỏ bánh xe, có xác định vật thể thuộc class motorcycle không |  |
