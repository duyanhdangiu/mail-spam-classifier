# Email Spam Classification on Google Colab

## Tiếng Việt

File chính: `email_spam_classification_colab.ipynb`

### Cách chạy trên Colab

1. Mở [Google Colab](https://colab.research.google.com/).
2. Chọn `File > Upload notebook`.
3. Tải lên file `email_spam_classification_colab.ipynb`.
4. Chọn `Runtime > Change runtime type > T4 GPU`.
5. Chọn `Runtime > Run all`.

Notebook tự tải bộ dữ liệu email công khai
[`SetFit/enron_spam`](https://huggingface.co/datasets/SetFit/enron_spam).
Không cần tải dữ liệu thủ công.

Mặc định, `FAST_RUN = True` dùng 18.000 email để phù hợp với Colab miễn
phí. Đổi thành `FAST_RUN = False` nếu muốn huấn luyện trên toàn bộ dữ liệu
sau khi làm sạch.

### Nội dung

- Phân tích dữ liệu và tiền xử lý văn bản.
- Baseline truyền thống: Multinomial Naive Bayes, Logistic Regression,
  Linear SVM với TF-IDF.
- Mô hình học sâu: Bidirectional LSTM và Bidirectional GRU.
- So sánh Accuracy, Precision, Recall, F1-score, ROC-AUC và thời gian train.
- Confusion matrix, phân tích lỗi, dự đoán email mới và xuất bảng CSV.
- Phần giải thích và kết luận song ngữ Việt - Anh.

## English

Main file: `email_spam_classification_colab.ipynb`

Upload the notebook to [Google Colab](https://colab.research.google.com/),
select `Runtime > Change runtime type > T4 GPU`, and run all cells.

The notebook automatically downloads the public
[`SetFit/enron_spam`](https://huggingface.co/datasets/SetFit/enron_spam)
dataset. By default, `FAST_RUN = True` uses 18,000 emails for a free Colab
session. Set it to `False` to train on the complete cleaned dataset.

## Browser test page

Open `email_spam_test.html` directly in a browser. The default local mode uses
keyword rules so the interface works without a server. It is a UI demo, not a
prediction from the trained notebook models.

To connect a trained model later, select `Model API endpoint` in the page. The
page sends `{"text": "email content"}` with an HTTP POST request and accepts a
response such as `{"prediction": "spam", "score": 0.98}`.

## Publish with GitHub Pages

The repository includes `index.html`, so the browser demo can be published
from the repository root:

1. Push this repository to GitHub.
2. Open `Settings > Pages`.
3. Under `Build and deployment`, select `Deploy from a branch`.
4. Select the `main` branch and `/(root)` folder, then save.

The public URL will have the form:
`https://<github-user>.github.io/<repository>/`.
