### 📝 List bài toán của tôi:
| # | Subsidiary (VinFast/Xanh SM...) | Lens | Mô tả ngắn bài toán |
|---|----------------------------------|------|---------------------|
| 1 |**XanhSM** | Pain từ người khác | Tài xế không biết nhu cầu khách hàng, như bật điều hòa quá lạnh hay mở nhạc không đúng gu khách |
| 2 |**VinMec** | Ai-Upgrade | Bệnh nhân có nhiều tiền sử bệnh lý khác nhau nên cần những phương pháp lộ trình khác nhau |
| 3 |**VinMec** | Tốn thời gian| Các thủ tục của bệnh viện liên quan đến BHXH,... rườm rà và mất thời gian cho nhân viên sàng lọc |
| 4 |**VinMec** | Lặp lại| Các bác sĩ, bệnh nhân sẽ phải thường xuyên hỏi bệnh nhân để nắm bắt được bệnh án |
| 5 |**VinMec** | Pain từ người khác | Không diễn tả đúng tình trạng bệnh để có thể chuẩn đoán đúng |
| 6 |**VinMec** | Ai-Upgrade| Các chuẩn đoán về bệnh mới cần cập nhật để tránh dịch bệnh lan rộng |

---

# 🃏 Phase 2 — QUICK-ASSESS (Cá nhân, 30 min)

Chọn **top 3 bài toán** từ danh sách trên và hoàn thiện **3 Quick Problem Cards** dưới đây (10 phút/card).

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #1                                     │
│                                                             │
│ Bài toán (1 câu): Tự động hóa khâu thu thập tiền sử bệnh lý và triệu chứng ban đầu │
│                   của bệnh nhân trước khi vào gặp bác sĩ.  │
│ Công ty thành viên: [ ] VinFast  [ ] Xanh SM  [ ] Vinhomes  │
│                     [x] Vinmec   [ ] Khác (Ghi rõ)________  │
│                                                             │
│ Ai đang đau (Actor)? Bệnh nhân (đợi lâu) & Bác sĩ (tốn thời gian khai thác lại từ đầu) │
│                                                             │
│ Workflow thủ công hiện tại (3-5 bước):                      │
│   1. Bệnh nhân đến viện ──> 2. Điều dưỡng hỏi trực tiếp triệu chứng/đo chỉ số sinh tồn│
│   ──> 3. Bác sĩ ngồi khai thác lại tiền sử và gõ text vào hệ thống bệnh án điện tử     │
│                                                             │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2 & 3: Khai thác tiền sử và triệu chứng lâm  │
│                                  sàng (Tốn 15-20 phút của bác sĩ/bệnh nhân).     │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Gửi Form khảo sát │
│ trên App Vinmec khi đặt lịch. Bệnh nhân tích chọn triệu chứng, hệ thống tự động đẩy │
│ dữ liệu cấu trúc vào màn hình của Bác sĩ trước giờ hẹn. │
│                                                             │
│ Đo thành công bằng gì (Metric có số)? │   - Giảm thời gian bác sĩ phải gõ máy khai thác tiền sử từ 15 phút ──> dưới 3 phút. │
│   - Tăng công suất phục vụ của 1 phòng khám lên ──> 25% mỗi ngày.│
│   VD: "Giảm thời gian soạn phản hồi từ 10 min ──> under 2 min"│
│                                                             │
│ Quick Architecture: [x] No AI  [] Rule  [ ] LLM  [ ] Agent │
└─────────────────────────────────────────────────────────────┘
```

```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #2                                     │
│                                                             │
│ Bài toán (1 câu): Tự động hóa việc đọc, tóm tắt và cấu trúc hóa lịch sử bệnh lý     │
│                   từ hồ sơ cũ (bản quét/file ảnh/giấy viết tay) của bệnh nhân.       │
│                                                                                     │
│ Công ty thành viên: [ ] VinFast   [ ] Xanh SM   [ ] Vinhomes                        │
│                     [x] Vinmec    [ ] Khác (Ghi rõ)________                         │
│                                                                                     │
│ Ai đang đau (Actor)? Bác sĩ (Tốn thời gian lội ngược dòng lịch sử y tế của ca khó) │
│                                                                                     │
│ Workflow thủ công hiện tại (3-5 bước):                                              │
│   1. Bệnh nhân mang tập hồ sơ/bệnh án cũ từ viện khác đến ──> 2. Bác sĩ phải ngồi   │
│   đọc thủ công từng trang, lọc tìm các thông tin cốt lõi (bệnh nền, kết quả giải    │
│   phẫu bệnh, đơn thuốc cũ) ──> 3. Bác sĩ tự tóm tắt lại và gõ vào hệ thống Vinmec.  │
│                                                                                     │
│ Bước nào tốn thời gian/lỗi nhất? Bước 2 & 3: Đọc hiểu và tổng hợp thông tin từ      │
│                                  văn bản tự do (Tốn 15-30 phút/ca bệnh phức tạp).   │
│                                                                                     │
│ AI có thể nhảy vào hỗ trợ ở bước nào? Tiếp nhận file quét hồ sơ cũ, dùng LLM chuyên │
│ biệt y tế (đã bóc tách qua OCR) để đọc hiểu, trích xuất thực thể y tế (Named Entity │
│ Recognition) và tóm tắt thành dạng bảng (JSON) để đẩy thẳng vào bệnh án điện tử.   │
│                                                                                     │
│ Đo thành công bằng gì (Metric có số)?                                               │
│   - Giảm thời gian bác sĩ nghiên cứu hồ sơ cũ từ 20 phút ──> dưới 2 phút/ca.        │
│   - Tỷ lệ trích xuất đúng các thông tin cốt lõi (dị ứng, bệnh nền) đạt ──> trên 95%.│
│                                                                                     │
│ Quick Architecture: [ ] No AI   [ ] Rule   [x] LLM   [ ] Agent     │
└─────────────────────────────────────────────────────────────┘

```


```
┌─────────────────────────────────────────────────────────────┐
│ QUICK PROBLEM CARD #3                                     │
│                                                             │
│ Bài toán (1 câu): Tự động giám sát, cập nhật các phác đồ chẩn đoán dịch bệnh mới    │
│                   trên thế giới để cảnh báo và nâng cấp hệ thống lâm sàng Vinmec.  │
│                                                                                     │
│ Công ty thành viên: [ ] VinFast   [ ] Xanh SM   [ ] Vinhomes                        │
│                     [x] Vinmec    [ ] Khác (Ghi rõ)________                         │
│                                                                                     │
│ Ai đang đau (Actor)? Ban Giám đốc chuyên môn, Hội đồng Kiểm soát nhiễm khuẩn Vinmec │
│                                                                                     │
│ Workflow thủ công hiện tại (3-5 bước):                                              │
│   1. Hội đồng y khoa đọc thủ công báo cáo dịch tễ (WHO, CDC, Bộ Y tế) ──> 2. Họp bàn│
│   đánh giá nguy cơ dịch bệnh ──> 3. Cập nhật thủ công phác đồ và gửi email nhắc nhở │
│   toàn bộ bác sĩ trong hệ thống y tế Vinmec (Mất từ 1-2 tuần).                      │
│                                                                                     │
│ Bước nào tốn thời gian/lỗi nhất? Bước 1 & 3: Giám sát nguồn thông tin khổng lồ toàn │
│                    cầu và cập nhật, triển khai phác đồ mới xuống các phòng khám.   │
│                                                                                     │
│ AI có thể nhảy vào hỗ trợ ở bước nào? AI Agent tự động vận hành (Autonomous Engine):│
│ Quét tài liệu y khoa thời gian thực ──> Đối chiếu với cơ sở dữ liệu phác đồ hiện tại│
│ của Vinmec ──> Dự thảo bản cập nhật chẩn đoán ──> Đẩy thông báo khẩn cấp đến bác sĩ.│
│                                                                                     │
│ Đo thành công bằng gì (Metric có số)?                                               │
│   - Giảm thời gian cập nhật phản ứng với dịch bệnh mới từ 7 ngày ──> dưới 6 giờ.    │
│   - Tỷ lệ bỏ sót thông báo dịch bệnh khẩn cấp (WHO/CDC) giảm về ──> 0%.             │
│                                                                                     │
│ Quick Architecture: [ ] No AI   [ ] Rule   [ ] LLM   [x] Agent    │
└─────────────────────────────────────────────────────────────┘

```
> [!TIP]
> **🤖 AI Prompts — Stress-Test thẻ bài toán:**
> Hãy dán nội dung thẻ bài toán của bạn vào LLM để nhận phản biện:
> *"Đây là một thẻ bài toán vận hành tôi đề xuất cho Vin Smart Future: [Dán nội dung]. Hãy đóng vai trò là một CFO và Trưởng phòng Vận hành cực kỳ khắt khe, chỉ ra cho tôi 3 điểm yếu về logic, metric, và giải thích vì sao rule-based code thông thường có thể giải quyết bài toán này tốt hơn là dùng AI."*