#  Vietnamese Food VQA System — Deep Learning Project

>  Project | Deep Learning | Ton Duc Thang University | 2026

## Thành viên
| MSSV | Họ tên |
|------|--------|
| 523H0159 | Nguyen Thai Khanh Nam |
| 523H0174 | Tran Van Qui |
| 523H0186 | Le Khac Thanh Tri |

---

##  Tổng quan
Hệ thống **Hỏi-Đáp Trực Quan (VQA)** cho món ăn Việt Nam.  
Đầu vào: ảnh món ăn + câu hỏi tiếng Việt → Đầu ra: câu trả lời ngắn gọn.

Dataset: **2.100 ảnh**, 30 class món ăn, ~6.300 cặp Q&A tiếng Việt  
(sinh bằng Gemini 2.5 Flash)

---

##  Các hướng tiếp cận

| Notebook | Approach | Mô tả |
|----------|----------|-------|
| `00_data_preprocessing.ipynb` | Data | Lấy mẫu, gọi Gemini API sinh Q&A |
| `A1_vit_phobert_lstm_decoder.ipynb` | Hướng A1 | ViT + PhoBERT + LSTM Decoder + Spatial Attention |
| `A2_vit_phobert_transformer_decoder.ipynb` | Hướng A2 | ViT + PhoBERT + Transformer Decoder (4 lớp, 8 heads) |
| `B1_blip2_zeroshot.ipynb` | Hướng B1 | BLIP-2 Zero-shot (3.7B params, không fine-tune) |
| `B2_blip2_lora_finetuned.ipynb` | Hướng B2 | BLIP-2 + LoRA Fine-tuned (r=16) |

---

## 🗂️ Dataset & Model Weights
📁 Google Drive: [Xem tại đây](https://drive.google.com/drive/folders/1jBz2iUq5_4D4beTpUFuFH9Xuxp3NfryH)

Dataset **không** có trong repo vì kích thước lớn.  
Tải về và đặt vào thư mục `data/` trước khi chạy.

---

## ⚙️ Chạy trên Google Colab
1. Mở notebook muốn chạy trên Colab
2. Mount Google Drive để truy cập dataset
3. Cài thư viện cần thiết (có cell hướng dẫn trong mỗi notebook)

##  Đánh giá
Metrics: BLEU-1, BLEU-4, ROUGE-L, METEOR, BERTScore (F1)  
BERTScore dùng `bert-base-multilingual-cased` cho tiếng Việt.
