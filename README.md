# Git_Flow

## 1. Workflow cơ bản

<div align="center">
<img width="600" alt="image" src="https://github.com/user-attachments/assets/3d713555-3867-49d8-85e3-76413678e728" />
</div>

**Ở nhánh main/master ta sẽ không viết code ở đây**

**Tạo ra nhánh develop (Nơi sẽ phát triển code)**

```
git checkout -b develop
```

1. **Quản lý** sẽ tạo issues trong đây

<img width="600" alt="1" src="https://github.com/user-attachments/assets/732aed61-934b-46e9-a6a4-8b80d5677d18" />

2. **Dev** sẽ vào đây để check công việc, chú ý tag #1 như hình dưới. Đây là số thứ tự task công việc

<img width="600" alt="2" src="https://github.com/user-attachments/assets/3bfccd9e-528f-4d45-a173-6944a8ebd6bf" />

Bây giờ thì ta sẽ tạo nhánh mới `feature/1-add-cart-model` (Tùy vào dự án mà cách đặt tên nhánh cũng sẽ khác nhau). Khi hoàn thành công việc ta đẩy code lên nhánh đó thôi

```
git checkout -b feature/1-add-cart-model
git add .
git commit -m "#1 - add cart model"
git push 
```

<img width="600" alt="3" src="https://github.com/user-attachments/assets/fd00d816-3302-4e73-ba39-88354edcd88a" />

Trong đây chúng ta cần chú ý về việc đặt tên cho commit (Tùy vào dự án mà cách đặt tên nhánh cũng sẽ khác nhau). Nên đặt `#1` (hay `#[số thứ tự task]`) giúp cho việc khi push code lên github, nó sẽ xuất hiện ngay trong issues đó

<img width="600" alt="4" src="https://github.com/user-attachments/assets/a83231b1-2586-4d0d-adb3-5c775d8a3408" />

**3. Quản lý** sẽ review code và quyết định merge code vào nhánh develop hay không. Chúng ta có thể thấy `#1` sẽ tham chiếu tới người code task đó

<img width="600" alt="5" src="https://github.com/user-attachments/assets/91c5113a-cf77-46e7-b56f-9bd48483ec4b" />

<img width="600" alt="6" src="https://github.com/user-attachments/assets/cd28daec-eeaa-4cf5-8b41-30b456812fa8" />

<img width="600" alt="7" src="https://github.com/user-attachments/assets/1bce1fa4-6ce8-482c-b24c-efef969453ca" />

Chúng ta có thể thấy code đã được merge vào nhánh develop

**4. Dev**
