# Git_Flow

## I. Workflow

### 1. Workflow cơ bản

<div align="center">
<img width="600" alt="image" src="https://github.com/user-attachments/assets/3d713555-3867-49d8-85e3-76413678e728" />
</div>

**Ở nhánh main/master ta sẽ không viết code ở đây**

**Tạo ra nhánh develop (Nơi sẽ phát triển code)**

```
git checkout -b develop
```

**1. Quản lý** sẽ tạo issues trong đây

<div align="center">
<img width="800" alt="1" src="https://github.com/user-attachments/assets/732aed61-934b-46e9-a6a4-8b80d5677d18" />
</div>

**2. Dev** sẽ vào đây để check công việc, chú ý tag #1 như hình dưới. Đây là số thứ tự task công việc

<div align="center">
<img width="800" alt="2" src="https://github.com/user-attachments/assets/3bfccd9e-528f-4d45-a173-6944a8ebd6bf" />
</div>

Bây giờ thì ta sẽ tạo nhánh mới `feature/1-add-cart-model` (Tùy vào dự án mà cách đặt tên nhánh cũng sẽ khác nhau). Khi hoàn thành công việc ta đẩy code lên nhánh đó thôi

```
git checkout -b feature/1-add-cart-model
git add .
git commit -m "#1 - add cart model"
git push 
```

<div align="center">
<img width="800" alt="3" src="https://github.com/user-attachments/assets/fd00d816-3302-4e73-ba39-88354edcd88a" />
</div>
Trong đây chúng ta cần chú ý về việc đặt tên cho commit (Tùy vào dự án mà cách đặt tên nhánh cũng sẽ khác nhau). Nên đặt `#1` (hay `#[số thứ tự task]`) giúp cho việc khi push code lên github, nó sẽ xuất hiện ngay trong issues đó

<div align="center">
<img width="800" alt="4" src="https://github.com/user-attachments/assets/a83231b1-2586-4d0d-adb3-5c775d8a3408" />
</div>

**3. Quản lý** sẽ review code và quyết định merge code vào nhánh develop hay không. Chúng ta có thể thấy `#1` sẽ tham chiếu tới người code task đó

<div align="center">
<img width="800" alt="5" src="https://github.com/user-attachments/assets/91c5113a-cf77-46e7-b56f-9bd48483ec4b" />
</div>
<div align="center">
<img width="800" alt="6" src="https://github.com/user-attachments/assets/cd28daec-eeaa-4cf5-8b41-30b456812fa8" />
</div>
<div align="center">
<img width="800" alt="7" src="https://github.com/user-attachments/assets/1bce1fa4-6ce8-482c-b24c-efef969453ca" />
</div>

Chúng ta có thể thấy code đã được merge vào nhánh develop

**4. Dev** muốn code tiếp thì sẽ về nhánh develop sử dụng câu lệnh `git pull`

```
git pull
git pull origin [tên_nhánh_cần_pull]
```

Xong đứng từ nhánh develop xong tạo nhánh mới như hình dưới mô tả:

```
git checkout -b [tên_nhánh]
```

<div align="center">
<img width="800" alt="image" src="https://github.com/user-attachments/assets/00d0414f-5bab-4be8-ba87-2b3428c30aed" />
</div>

**5. Quản lý** sau khi code ở nhánh develop đã hoàn thành, chuyển sang giai đoạn release

Đứng tại nhánh develop

```
git checkout -b release-1.0.0
git merge develop
git push
```

<div align="center">
<img width="800" alt="image" src="https://github.com/user-attachments/assets/e9f37929-ab8c-4b20-9e57-480111c51c91" />
</div>

Sau khi release xong có quyết định merge vào nhánh main/master. Từ nhánh main/master sẽ có quyết định đẩy code lên production

<div align="center">
<img width="800" alt="image" src="https://github.com/user-attachments/assets/208f7c35-aa26-4ceb-9073-68d464dceb64" />
</div>

## II. Các lệnh git cơ bản và nâng cao

### 1. Các lệnh git cơ bản và nâng cao

<img src="https://github.com/CUNGVANTHANG/Commands/assets/96326479/c0d57440-e3dc-47fd-afd5-8103d65af17e" width="400px">

<img src="https://github.com/CUNGVANTHANG/Commands/assets/96326479/60358644-b4d5-49c7-84f3-05d6a53986de" width="400px" >

| Câu lệnh | Ý nghĩa |
| :-- | :-- |
| `git -v` | Kiểm tra phiên bản của Git |
| `git init` | Khởi tạo `.git` trong thư mục dự án của bạn |
| `git clone https://github.com/...` | Nhân bản (clone) dự án từ kho lưu trữ từ xa (remote repository) về máy |
| `git config --g user.name "Tên của bạn"` | Cài đặt thông tin cá nhân |
| `git config --g user.email “Địa chỉ email của bạn” ` | Cài đặt thông tin cá nhân | 
| `git config --list` | Kiểm tra thông tin người đang thực hiện thay đổi |
| `git status` | Kiểm tra trạng thái (status) của kho lưu trữ (repository) |
| `git add .` | Thêm (add) những thay đổi (bạn đã tạo mới hoặc chỉnh sửa) để thực hiện commit |
| `git commit -m "Thông điệp của bạn"` | Ghi lại các thay đổi (change) vào kho lưu trữ (repository)  |
| `git push` | Push (đẩy) tất cả mọi thay đổi (đã commit) lên remote repository |
| `git push -u origin branch_mane` | Push (đẩy) branch vào remote repository |
| `git push -d origin branch_mane` | Xóa (delete) một branch trên remote repository | 
| `git branch -M branch_name (main)` | Đổi tên nhánh chính |
| `git branch` | Kiểm tra các nhánh hiện có của bạn ở local | 
| `git branch -c branch_name` hoặc `git checkout -b branch_name` | Tạo một nhánh có tên "branch_name" và hợp nhất (merge) nó với nhánh chính. |
| `git branch -d branch_name` | Xóa một nhánh tại local có tên: "branch_name" (branch đã được hợp nhất (push) vào remote repository) |
| `git branch -D branch_name` | Xóa một nhánh tại local có tên: "branch_name" (branch đã commit nhưng chưa hợp nhất vào remote repository) |
| `git branch -a` | Kiểm tra các branch hiện có trên remote repo của bạn. | 
| `git checkout branch_name` | Lệnh trên giúp di chuyển không gian làm việc, kiểm tra tệp giữa các branch_name. |
| `git fetch origin` | Xác nhận nội dung thay đổi trong branch của remote repository nhưng nội dung branch của local repository không bị thay đổi. | 
| `git merge branch_name2` | Merge kết hợp nhánh hiện tại, với một nhánh được chỉ định (nhớ phải `git checkout branch_name1`: Nhánh nhận hợp nhất hoặc nhánh hiện tại) |
| `git pull origin main` | Git pull kéo tất cả các thay đổi từ main về local |
| `git pull` | Git pull kéo tất cả các thay đổi từ branch_name về local |
| `git pull origin` | Git pull kéo tất cả các thay đổi từ kho lưu trữ từ xa vào branch bạn đang làm việc. (pull là sự kết hợp của 2 lệnh khác nhau: fetch và merge) |
| `git pull --rebase` | Cách pull chống xung đột |
| `git stash` | Lưu lại công việc đang làm ở branch này để chuyển sang branch khác (Khi bạn chưa muốn commit code) |
| `git stash list` | Xem lại lịch sử thay đổi |
| `git stash show stash@{n}` | Xem lại lịch sử thay đổi cụ thể của lần stash save{n}. |
| `git stash clear` | Xoá toàn bộ stash |
| `git rebase branch_name2` | Code từ branch_name2 được hợp nhất vào branch_name1 (nhớ phải `git checkout branch_name1`: Di chuyển về nhánh nhận sự hợp nhất) |
| `git revert <commit_id>` | Lệnh này tạo commit đảo ngược commit có commit_id được chọn. | 
| `git reset –hard <commit_id>` | Lệnh này xoá toàn bộ các commit trước đó, đưa branch về trạng thái của commit_id được chọn. | 
| `git reset –soft <commit_id>` | Đưa branch về trạng thái của commit_id được chọn. Giữ nguyên tất cả thay đổi của file và các thay đổi ở stage. (Được khuyến khích sử dụng) |

_Chú ý:_

- Merge: Chỉ lấy nội dung commit cuối cùng của hai nhánh, tích hợp tạo thành commit mới. Các commit trước đó được giữ nguyên không thay đổi.
- Rebase: Lấy code từ branch_name2, từ những commit ở branch_name2 tích hợp đồng thời tái tạo lại commit mới ở branch_name1 (Các commit đã tồn tại bị bỏ đi).

### 2. Cách khắc phục một số lỗi 

#### 1. Các khắc phục lỗi hỗ trợ xác thực mật khẩu bị xóa trên GitHub

Lỗi:

![image](https://github.com/CUNGVANTHANG/Commands/assets/96326479/bbd6ceb8-f276-4fd6-9328-8e8f86536d32)

Khắc phục:

Bước 1: Vào **Settings/Developer Settings**

![image](https://github.com/CUNGVANTHANG/Commands/assets/96326479/dc48d419-6bcc-4501-8f04-e20ca1ebc8c4)

Bước 2: Chọn **Generate new token/Generate new token (classic)**

![image](https://github.com/CUNGVANTHANG/Commands/assets/96326479/0da2ed88-b9cf-410b-afb2-7a6e00e3aad2)

Bước 3: 

![image](https://github.com/CUNGVANTHANG/Commands/assets/96326479/b416b44d-7f86-419d-9f29-baccd0675acb)

Bước 4: Chọn tất cả, xong **Generate token**

![image](https://github.com/CUNGVANTHANG/Commands/assets/96326479/86cf3884-1e0f-4914-869a-b6ec2d53bdf6)

Bước 5: Gõ `git remote set-url origin https://<token>@github.com/<username>/<repositories>

```
git remote set-url origin https://<token>@github.com/CUNGVANTHANG/Commands
```

Bước 6:

```
git push origin main
```

#### 2. Các khắc phục không .gitignore được

[Tham khảo tại đây](https://stackoverflow.com/questions/45400361/why-is-gitignore-not-ignoring-my-files)

Sử dụng câu lệnh để xóa khỏi kho lưu trữ các tệp được theo dõi

```
git rm -r --cached .
```

_Ví dụ:_

```
git rm -r --cached ./node_modules
```
