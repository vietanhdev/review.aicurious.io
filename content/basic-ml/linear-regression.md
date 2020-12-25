---
title: "Linear Regression - Hồi quy tuyến tính"
weight: 10
---

![Hồi quy tuyến tính](https://aicurious.io/posts/linear-regression/output_6_1.png)

> Phân tích hồi quy tuyến tính là một phương pháp phân tích quan hệ giữa biến phụ thuộc Y với một hay nhiều biến độc lập X. Mô hình hóa sử dụng hàm tuyến tính (bậc 1). Các tham số của mô hình (hay hàm số) được ước lượng từ dữ liệu. - **Wikipedia**

- Input của bài toán là các giá trị $\mathbf{x} = [x_1, x_2, x_3, \dots, x_n]$
- Output của mô hình $ \hat{y} = f(\mathbf{x}) \approx y $ với $y$ là giá trị thực tế.

## Lời giải

Với các cặp $(\mathbf{x}_i, y_i), i = 1, 2, \dots, N$, hàm mất mát có giá trị

$$
\mathcal{L}(\mathbf{w}) = \frac{1}{2}\sum_{i=1}^N (y_i - \mathbf{\bar{x}_i}\mathbf{w})^2
$$

Giải bài toán chính là đi tìm điểm tối ưu:

$$
\mathbf{w}^* = \arg\min_{\mathbf{w}} \mathcal{L}(\mathbf{w})
$$

Đặt $\mathbf{y} = [y_1; y_2; \dots; y_N]$ là một vector cột chứa tất cả các output của training data; $\mathbf{\bar{X}} = [\mathbf{\bar{x}}_1; \mathbf{\bar{x}}_2; \dots; \mathbf{\bar{x}}_N ]$ là ma trận dữ liệu đầu vào (mở rộng) mà mỗi hàng của nó là một điểm dữ liệu. Ta có:

$$
\mathcal{L}(\mathbf{w}) = \frac{1}{2} \|\mathbf{y} - \mathbf{\bar{X}}\mathbf{w} \|_2^2
$$


Đạo hàm theo $w$ của hàm mất mát là:

$$
\frac{\partial{\mathcal{L}(\mathbf{w})}}{\partial{\mathbf{w}}} 
= \mathbf{\bar{X}}^T(\mathbf{\bar{X}}\mathbf{w} - \mathbf{y})
$$

Phương trình đạo hàm bằng 0 tương đương với:

$$
\mathbf{\bar{X}}^T\mathbf{\bar{X}}\mathbf{w} = \mathbf{\bar{X}}^T\mathbf{y} \triangleq \mathbf{b}
$$

Nghiệm tối ưu với giả nghịch đảo:

$$
\mathbf{w} = \mathbf{A}^{\dagger}\mathbf{b} = (\mathbf{\bar{X}}^T\mathbf{\bar{X}})^{\dagger} \mathbf{\bar{X}}^T\mathbf{y}
$$

Phương pháp tìm lời giải như trên sử dụng các kiến thức của đại số tuyến tính. Ngoài ra, ta có thể tìm lời giải cho bài toán này sửu dụng gradient descent. Tham khảo tại [đây](https://www.howkteam.vn/course/machine-learning-co-ban-voi-numpy/thuat-toan-gradient-descent-cho-linear-regression-3997).

## Regularization

L1, L2, Elastic Net

## Non-linearity

Làm thế nào để áp dụng cho các dữ liệu không tuyến tính?

## Tài liệu tham khảo

- https://machinelearningcoban.com/2016/12/28/linearregression/
- https://www.howkteam.vn/course/machine-learning-co-ban-voi-numpy/thuat-toan-gradient-descent-cho-linear-regression-3997

This page hasn't been completed. Create pull request [here](https://github.com/vietanhdev/review.aicurious.io/) to contribute.