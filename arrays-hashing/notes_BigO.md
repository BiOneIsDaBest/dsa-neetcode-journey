# Week 1 - Big O Basics

## Big O là gì?

Big O dùng để đo xem chương trình chạy nhanh hay chậm khi lượng dữ liệu tăng lên.

Ví dụ:

* Có 10 phần tử.
* Có 1000 phần tử.
* Có 1 triệu phần tử.

Big O giúp trả lời câu hỏi:

> "Nếu dữ liệu lớn hơn thì code của mình sẽ chậm đến mức nào?"

---

# O(1) - Constant Time

## Ý nghĩa

Dù có bao nhiêu dữ liệu thì chương trình vẫn chỉ thực hiện một số thao tác cố định.

Ví dụ:

```python
nums = [10, 20, 30, 40]

print(nums[0])
```

Máy tính thực hiện:

```text
Lấy phần tử ở index 0
In ra 10
```

Chỉ thực hiện đúng 1 thao tác truy cập.

=> O(1)

## Dấu hiệu nhận biết

* Truy cập phần tử bằng index.

```python
nums[0]
nums[5]
nums[100]
```

* Không cần duyệt toàn bộ mảng.

---

# O(n) - Linear Time

## Ý nghĩa

Nếu có n phần tử thì chương trình sẽ chạy khoảng n lần.

Dữ liệu tăng gấp đôi -> thời gian chạy tăng gần gấp đôi.

Ví dụ:

```python
nums = [10, 20, 30, 40]

for num in nums:
    print(num)
```

Máy tính thực hiện:

```text
num = nums[0] = 10 -> print(10)
num = nums[1] = 20 -> print(20)
num = nums[2] = 30 -> print(30)
num = nums[3] = 40 -> print(40)
```

Có 4 phần tử -> chạy 4 lần.

Nếu có 100 phần tử -> chạy 100 lần.

=> O(n)

## Dấu hiệu nhận biết

```python
for x in nums:
```

hoặc

```python
for i in range(len(nums)):
```

hoặc

```python
while i < len(nums):
```

=> Duyệt toàn bộ mảng 1 lần.

---

# O(n²) - Quadratic Time

## Ý nghĩa

Với mỗi phần tử, chương trình lại duyệt toàn bộ mảng thêm một lần nữa.

Ví dụ:

```python
nums = [1, 2, 3]

for i in nums:
    for j in nums:
        print(i, j)
```

Máy tính thực hiện:

```text
1 1
1 2
1 3

2 1
2 2
2 3

3 1
3 2
3 3
```

Có:

```text
3 x 3 = 9 lần chạy
```

Nếu có:

```text
100 phần tử
```

thì:

```text
100 x 100 = 10,000 lần chạy
```

=> O(n²)

## Dấu hiệu nhận biết

```python
for i in nums:
    for j in nums:
```

Hai vòng lặp lồng nhau trên cùng tập dữ liệu.

---

# Quy tắc tính Big O

## 1. Hai vòng lặp nối tiếp nhau

```python
for i in nums:
    print(i)

for j in nums:
    print(j)
```

Big O:

```text
O(n) + O(n)
= O(2n)
= O(n)
```

=> Cộng lại.

---

## 2. Hai vòng lặp lồng nhau

```python
for i in nums:
    for j in nums:
        print(i, j)
```

Big O:

```text
O(n × n)
= O(n²)
```

=> Nhân với nhau.

---

## 3. Giữ lại phần tăng nhanh nhất

Ví dụ:

```text
O(n + n²)
```

Ta giữ:

```text
O(n²)
```

Vì khi dữ liệu rất lớn:

```text
n² lớn hơn rất nhiều so với n
```

Ví dụ:

```text
n = 1000
n² = 1,000,000
```

---

# Mẹo nhớ nhanh

* Truy cập bằng index -> O(1)
* 1 vòng lặp qua mảng -> O(n)
* 2 vòng lặp lồng nhau -> O(n²)
* 2 vòng lặp tách riêng -> O(n)
* Nhiều Big O cộng lại -> giữ cái lớn nhất

---

# Checklist

* [x] Hiểu O(1)
* [x] Hiểu O(n)
* [x] Hiểu O(n²)
* [x] Biết khi nào cộng Big O
* [x] Biết khi nào nhân Big O
* [x] Biết giữ lại thành phần lớn nhất

---

# Điều học được

* Big O dùng để đo tốc độ chạy của chương trình.
* O(n²) thường chậm hơn rất nhiều so với O(n).
* Trong DSA, mục tiêu thường là tối ưu từ O(n²) xuống O(n).

---

# Lỗi phổ biến

❌ Thấy 2 vòng lặp là nghĩ ngay O(n²).

Hãy kiểm tra:

* Hai vòng lặp tách riêng -> cộng.
* Hai vòng lặp lồng nhau -> nhân.

---

# GitHub Commit Suggestion

```text
Day 01 - Learned Big O basics (O(1), O(n), O(n²))
```
 