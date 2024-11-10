# Stock Analysis and Prediction using Ridge Regression and LSTM

## Mô tả dự án

Dự án này nhằm phân tích tổng quan các thông tin có giá trị về cổ phiếu của Việt Nam được xuất hiện ở trên sàn HOSE, đồng thời đưa ra dự đoán giá cổ phiếu cho các cổ phiếu trong nhóm VN30, sử dụng hai phương pháp khác nhau: Ridge Regression và LSTM (Long Short-Term Memory). Với dữ liệu lịch sử về giá đóng cửa của các cổ phiếu, tôi xây dựng các mô hình có thể dự đoán giá tương lai trong khoảng thời gian ngắn hạn. Đây là một dự án kết hợp giữa machine learning truyền thống (Ridge Regression) và deep learning (LSTM) để đưa ra các so sánh và đánh giá hiệu quả của từng phương pháp.

## Mô tả dữ liệu:

Bộ dữ liệu được thu thập từ website cafef, ghi nhận thông tin về giá trị của tất cả các loại cổ phiếu trong khoảng thời gian từ 30/12/2012 đến 18/10/2024. 

## Nội dung dự án

1. Tiền xử lý dữ liệu: 

- Để dự đoán chính xác giá cổ phiếu, dữ liệu lịch sử về giá đóng cửa (Close price) cần được chuẩn bị và làm sạch trước khi đưa vào mô hình. 

- Tiền xử lý bao gồm việc loại bỏ các giá trị bị thiếu hoặc ngoại lệ có thể gây nhiễu cho mô hình, chuẩn hóa dữ liệu để đảm bảo giá trị các cột có thang đo tương đồng, và chuyển đổi ngày tháng về định dạng phù hợp cho mô hình sử dụng. 

- Bên cạnh đó, để sử dụng LSTM, dữ liệu còn được chia thành các chuỗi có độ dài cố định dựa trên số ngày đã chọn (window size), nhằm cung cấp ngữ cảnh về xu hướng trước đó khi dự đoán giá cho ngày tiếp theo. Các bước chuẩn bị dữ liệu cẩn thận này giúp đảm bảo tính chính xác và khả năng khái quát hóa của mô hình khi huấn luyện và kiểm tra với dữ liệu thực tế.

2. Dự báo giá cổ phiếu: 

- Dữ liệu lịch sử sau khi đã qua tiền xử lý sẽ được chia thành tập train và tập test theo tỷ lệ 95:5, tức là 95% dữ liệu được sử dụng để huấn luyện mô hình và 5% còn lại để đánh giá mô hình. 

- Mục tiêu của việc chia dữ liệu này là để mô hình học từ tập train và kiểm tra khả năng dự đoán với dữ liệu mới trên tập test. Các phương pháp dự đoán được áp dụng bao gồm Ridge Regression và LSTM. Với Ridge Regression, dữ liệu đầu vào là các chuỗi giá trong quá khứ để dự đoán giá đóng cửa cho 15 ngày tiếp theo, tận dụng đặc điểm hồi quy tuyến tính có điều chỉnh để tránh hiện tượng overfitting. 

- Trong khi đó, mô hình LSTM xử lý dữ liệu dạng chuỗi thời gian, khai thác được các mối liên hệ dài hạn trong dữ liệu, giúp dự báo các biến động giá trong tương lai. Quá trình dự báo sẽ đưa ra các giá trị dự đoán so với thực tế, giúp phân tích và đánh giá hiệu quả của từng mô hình.

3. Đánh giá mô hình: 

- Sau khi dự báo giá cổ phiếu hoàn tất, hiệu quả của mỗi mô hình sẽ được đánh giá thông qua các chỉ số đo lường độ chính xác như MSE (Mean Squared Error), RMSE (Root Mean Squared Error), và MAE (Mean Absolute Error).

- MSE giúp đánh giá độ chênh lệch trung bình bình phương giữa giá trị dự đoán và giá trị thực tế, trong khi RMSE, là căn bậc hai của MSE, cung cấp cái nhìn trực quan hơn về mức độ sai lệch trung bình của dự đoán so với thực tế. MAE, đo lường chênh lệch trung bình tuyệt đối giữa dự đoán và thực tế, giúp đánh giá sai số dưới dạng giá trị thực tế. 

- Việc sử dụng cả ba chỉ số này giúp có được bức tranh toàn diện về hiệu quả của mỗi mô hình, từ đó xác định phương pháp dự đoán giá cổ phiếu tốt nhất cho tập dữ liệu VN30.




