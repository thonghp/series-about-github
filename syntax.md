# Syntax GIT

## Mục lục nội dung

- [1. Overview](#1-overview)
  - [1.1 VCS](#11-vcs)
  - [1.2 Repository](#12-repository)
  - [1.3 Quản lý phiên bản của tập tin](#13-quản-lý-phiên-bản-của-tập-tin)
- [2. Quy trình hoạt động](#2-quy-trình-hoạt-động)
- [3. Các lệnh git thường dùng](#3-các-lệnh-git-thường-dùng)
  - [3.1 Cấu hình lần đầu khi sử dụng git](#31-cấu-hình-lần-đầu-khi-sử-dụng-git)
  - [3.2 Dùng lần đầu tiên khi push lên github](#32-dùng-lần-đầu-tiên-khi-push-lên-github)
  - [3.3 Git add](#33-git-add)
  - [3.3 Git status](#33-git-status)
  - [3.4 Git commit](#34-git-commit)
  - [3.5 Git log](#35-git-log)
  - [3.6 Git push fetch pull clone](#36-git-push-fetch-pull-clone)
  - [3.7 Git branch merge](#37-git-branch-merge)
  - [3.8 Git checkout](#38-git-checkout)
  - [3.9 Git restore](#39-git-restore)
  - [3.10 Git diff](#310-git-diff)
  - [3.11 Git cherry pick](#311-git-cherry-pick)
  - [3.12 Git stash](#312-git-stash)
- [4. Commit chuẩn](#4-commit-chuẩn)

## 1. Overview

### 1.1 VCS

- **Version control system** hoặc **SCM - source control management**, hệ thống kiểm soát phiên bản phân tán.
- Giúp theo dõi và quản lý các thay đổi trong mã nguồn.
- Cho phép tạo ra các phiên bản khác nhau của mã nguồn.

### 1.2 Repository

- Là một nơi lưu trữ tất cả các lịch sử thay đổi của mã nguồn của một dự án.
- Nó có thể được tạo ra bằng cách sử dụng lệnh **`git init`**
- Mỗi repository được lưu trữ trên máy tính cục bộ hoặc trên một máy chủ trực tuyến

### 1.3 Quản lý phiên bản của tập tin

- Mỗi lần thực hiện một commit, nó sẽ tạo ra một bản sao của tất cả các tập tin.
- Thông qua việc tạo nhánh thì mỗi nhánh là một bản sao của tất cả các tập tin.

## 2. Quy trình hoạt động

![alt img](/assets/working-process.jpg)

![cycle file in git](/assets/cycle-file.png)

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

## 3. Các lệnh git thường dùng

- [x] Logout tài khoản trên máy tính cục bộ 🠊 truy cập **credential manager** sau đó chọn tài khoản muốn xoá.
- [x] **`dir`** 🠊 **hiển thị các file và thư mục** có trong thư mục chỉ định.
- [x] **`ls -a`** 🠊 **hiển thị các file** kể cả file **`.gitignore`**.
- [x] **Thoát màn hình** vim **`:q`** hoặc **`q`**.
- [x] **Tạo file** 🠊 **`touch <fileName>`**.
  - Vd: **`touch a.txt`**

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

---

### 3.1 Cấu hình lần đầu khi sử dụng git

- [x] **`git --version`** 🠊 **xem phiên bản** của git.
- [x] **`git config --list`** 🠊 xem danh sách các thiết lập cấu hình.
- [x] **`git config --global user.name "username"`** 🠊 **cấu hình tên** sử dụng trên hệ thống git.
- [x] **`git config --global user.email "email"`** 🠊 **cấu hình email** sử dụng trên hệ thống git.

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

---

### 3.2 Dùng lần đầu tiên khi push lên github

- [x] **`git init`** 🠊 **khởi tạo** 1 repository local, tạo ra 1 thư mục con ẩn **`.git`**.
- [x] **`git branch -M <master/main>`** 🠊 chuyển tên nhánh hiện tại và tất cả commit sang nhánh **main** (chỉ nên dùng lần đầu tiên khi đẩy lên github).
- [x] **`git remote add origin <url>`** 🠊 kết nối đến máy chủ (remote repository) tương ứng với **url** chỉ định.
  - Khi đã kết nối có thể push và pull các thay đổi trên repository của github.
- [x] **`git push -u origin <master/main>`** 🠊 đẩy kho local lên máy chủ.
  - **`-u`** 🠊 tuỳ chọn cho phép những lần sau git push không cần chỉ định nhánh trên máy chủ.
- [x] **`git push --set-upstream origin <branch_name>`** 🠊 push nhánh mới tạo lên nhánh remote. Sử dụng khi nhánh mới tạo và push lần đầu lên remote.

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

---

### 3.3 Git add

- [x] **`git add <file_name/dir_name>`** 🠊 thêm file/directory chỉ định vào khu vực stage (chuẩn bị commit).
  - **`git add <file_A> <file_B>`** 🠊 add 1 lúc nhiều file/directory.
  - **`git add .`** 🠊 thêm tất cả file, thư mục (kể cả con) vào khu vực stage bao gồm tập tin ẩn **`.ignore`**.
  - **`git add *`** 🠊 thêm tất cả file và thư mục kể cả con vào stage, bỏ qua tập tin ẩn **`.ignore`**.

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

---

### 3.3 Git status

- [x] **`git status`** 🠊 hiển thị trạng thái cây làm việc so với commit cuối.
  - Dòng thứ nhất hiện nhánh đang làm việc.
  - Dòng kế tiếp thể hiện trạng thái của file:
    - Nếu có file mới được thêm vào mà chưa **add** sẽ hiển thị tên file mới đó màu đỏ và ở trạng thái **Untracked**.
    - File **Untracked** sau khi **add** sẽ chuyển sang **changes to be committed** ở trạng thái **Staged** và hiển thị tên file mới đó sang màu xanh lá.
    - Sau khi commit sẽ ở chế độ **unmodified**.
    - Ở trạng thái **unmodified**, file thay đổi sẽ chuyển sang trạng thái **modified** màu đỏ.
    - Khi add file **modified** sẽ chuyển lại thành màu xanh.

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

---

### 3.4 Git commit

- [x] **`git commit -m "<message>"`** 🠊 ghi lại các thay đổi với kho lưu trữ. **Lưu ý** là file **Untracked** sẽ không được commit, chỉ commit các file đã **add**.
- [x] **`git reset --soft HEAD~1`** 🠊 huỷ commit cuối.
  - Vd: **commit cuối là c2** dùng để commit một file mới là b.txt. Lúc này nó sẽ **huỷ commit c2** và file b.txt sẽ quay lại trạng thái đã add nhưng chưa commit.
- [x] **`git reset --hard HEAD~1`** 🠊 xoá commit cuối và những thay đổi liên quan đến commit cuối.
- [x] **`git commit --amend -m "<message>"`** 🠊 Thêm file mới add vào commit cuối thay vì commit thêm 1 lần

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

---

### 3.5 Git log

- [x] **`git log`** 🠊 liệt kê lịch sử commit của repository. Bao gồm **commit hash, author, date, nội dung commit**.
  - **`git log --oneline`** 🠊 xem nội dung commit + commit hash ở dạng ngắn gọn trên 1 hàng.
  - **`git log --oneline --graph`** 🠊 xem nội dung commit + commit hash ở dạng ngắn gọn trên 1 hàng cùng với 1 đồ thị hiển thị mối quan hệ giữa branch và commit.

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

---

### 3.6 Git push fetch pull clone

- [x] **`git push`** 🠊 đẩy thay đổi cục bộ lên remote repository.
- [x] **`git fetch`** 🠊 tải xuống tất cả commit mới từ remote vào local repository.
  - Sử dụng **`git merge`** để hợp nhất với các nhánh local.
- [x] **`git pull`** 🠊 tải về các thay đổi remote xuống xuống local và merge vào local, lệnh này tương tự **git fetch + git merge**.
  - **`git pull <remote> <branch>`** 🠊 tải về các thay đổi remote của nhánh xuống xuống local. Vd **`git pull origin main`**
- [x] **`git clone <url>`** 🠊 **sao chép toàn bộ** lịch sử và tập tin của repository từ trên github về máy và đặt tên giống trên máy chủ. Ta có thể làm việc trên nó như một local repository.

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

---

### 3.7 Git branch merge

- [x] **`git branch`** 🠊 hiển thị các nhánh đang tồn tại.
  - **`git branch <branch_name>`** 🠊 tạo nhánh theo tên chỉ định, kế thứa **các commit** của nhánh **master** tính từ commit **cuối** trước khi tạo nhánh. Lúc này vẫn ở nhánh chính chưa chuyển nhánh.
  - **`git branch -m <old_branch_name> <new_brach_name>`** 🠊 đổi tên nhánh.
  - **`git branch -d <brachName>`** 🠊 xóa nhánh chỉ định.
- [x] **`git merge <branch_name>`** 🠊 merge nhánh

**Quy tắc đặt tên nhánh**

- Tên nhánh không nên chứa ký tự đặc biệt, trừ dấu gạch ngang **`-`** và dấu gạch dưới **`_`**.
- Tránh sử dụng tên nhánh trùng lặp.
- Nên dùng prefix cho tên nhánh để dễ phân biệt.
- Nên dùng chữ thường.
- Nên xoá nhánh chính sau khi merge.

**Một vài prefix thường dùng**

```git
master/main 🠊 Nhánh chính.
develop 🠊 Chứa version đang được phát triển của dự án.
feature 🠊 Liên quan đến phát triển tính năng.
          feature/login
release 🠊 Liên quan đến phát hành phiên bản mới.
hotfix 🠊 Liên quan đến sửa lỗi nghiêm trọng trong version chính thức.
          hotfix/fix-bug-login
bugfix 🠊 Liên quan đến sửa lỗi trong phiên bản đang phát triển.
staging 🠊 Liên quan đến kiểm tra trước khi đưa vào phiên bản chính thức.
```

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

---

### 3.8 Git checkout

**Tạo nhánh và chuyển nhánh**

- [x] **`git checkout <branch_name>`** 🠊 chuyển tới nhánh chỉ định.
- [x] **`git checkout -b <new_branch_name>`** 🠊 tạo nhánh mới và chuyển tới nhánh đó luôn.

**Khôi phục file ở commit cuối hoặc chỉ định**

- [x] **`git checkout <commit_hash>`** 🠊 chuyển tới commit có commit hash tương ứng, commit hash coi trong **`git log --oneline`**.
- [x] **`git checkout <commit_hash> -- <file_name>`** 🠊 khôi phục lại file tương ứng với commit hash chỉ định. Lúc này file sẽ ở trạng thái **modified** đã được add.
- [x] **`git checkout -- <file_name>`** 🠊 khôi phục lại file chỉ định thời điểm commit cuối.
  - Trường hợp **thay đổi** file commit cuối **chưa sử dụng lệnh git add** 🠊 file thay đổi sẽ khôi phục.
  - Trường hợp **thay đổi** file commit cuối và **sử dụng lệnh git add** 🠊 file thay đổi **không khôi phục** và ở trạng thái **modified của add**.
- [x] **`git checkout -f`** 🠊 khôi phục lại tất cả các file ở commit cuối.
  - Trường hợp **thay đổi file commit cuối** + **thêm file mới và sử dụng lệnh git add** 🠊 file thay đổi sẽ khôi phục, file thêm sẽ bị xoá.
- [x] **`git checkout -- .`** 🠊 Khôi phục lại tất cả file commit cuối.
  - Trường hợp **thay đổi file commit cuối** + **thêm file mới chưa sử dụng lệnh git add** 🠊 file thay đổi sẽ khôi phục, file thêm ở trạng thái untracked.
  - Trường hợp **thay đổi file commit cuối** + **thêm file mới và sử dụng lệnh git add** 🠊 file thay đổi **không khôi phục** và ở trạng thái **modified của add**, file thêm sẽ ở trạng thái **đã add**.

> Cả 2 lệnh **checkout -f và -- .** trong trường hợp **thay đổi file commit cuối** + **thêm file mới chưa sử dụng lệnh git add** 🠊 file thay đổi sẽ khôi phục, file thêm ở trạng thái untracked

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

---

### 3.9 Git restore

- [x] **`git restore <file_name>`** 🠊 tương đương với **`git checkout -- <file_name>`**.
- [x] **`git restore .`** 🠊 tương đương với **`git checkout -- .`**.

**Khôi phục lại file đã add về trạng thái chưa add**

- [x] **`git restore --staged <file_name>`** 🠊 khôi phục lại file đã add thành file chưa add.
  - Trường hợp file commit cuối thay đổi và sử dụng **`git add`** 🠊 Khôi phục trạng thái **modified đã add** thành **modified chưa add**.
  - Trường hợp file thêm mới và sử dụng **`git add`** 🠊 Khôi phục trạng thái **new file đã add** thành **untracked chưa add**.
- [x] **`git restore --staged .`** 🠊 khôi phục lại tất cả file đã add thành chưa add.

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

---

### 3.10 Git diff

- [x] **`git diff <commit_hash1> <lcommit_hash2>`** 🠊 Sự khác nhau giữa 2 commit.

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**

### 3.11 Git cherry pick

**Gộp commit chỉ định từ nhánh vào nhánh**

![alt](/assets/cherry-pick-1.png)

- [x] **`git cherry-pick <commit_hash>`** 🠊 merge commit chỉ định vào nhánh hiện tại.
  - Vd merge **commit T2** từ nhánh **branch1** vào nhánh **main** 🠊 **`git cherry-pick afaa1a0`**.
- [x] **`git cherry-pick <commit_hash1> <commit_hash2>`** 🠊 merge nhiều commit 1 lúc.
- [x] **`git cherry-pick <commit_hashT4>..<commit_hashT7>`** 🠊 merge commit T5,6,7.
- [x] **`git cherry-pick <commit_hashT4>^..<commit_hashT7>`** 🠊 merge commit T4,5,6,7.

### 3.12 Git stash

**Đưa file đang làm giữa chừng vào folder tạm để làm việc khác, chỉ áp dụng cho file đã commit và sửa đổi.**

![alt](/assets/stash.png)

- [x] **`git stash save '<name>'`** 🠊 đưa git vào stash theo tên đặt.
  - Vd: **`git stash save 'T1'`** 🠊 lưu vào stash đặt tên là T1.
- [x] **`git stash list`** 🠊 xem lại tất cả stash đang lưu.
- [x] **`git stash apply <stash_name>`** 🠊 lấy stash ra làm tiếp.
  - Vd: **`git stash apply stash@{0}`** 🠊 lấy ra stash T2.
- [x] **`git stash clear`** 🠊 xoá hết stash đã lưu. Dùng khi lấy stash ra và làm xong.

## 4. Commit chuẩn

- Commit ngắn không nên quá 50 từ
- **`<type>`**
  - **`feat`**: Thêm một tính năng
  - **`fix`**: fix bug cho hệ thống, vá lỗi trong codebase
  - **`docs`**: thêm/thay đổi document
  - **`style`**: những thay đổi không làm thay đổi ý nghĩa của code như thay đổi css/ui
  - **`refactor`**: sửa code nhưng không fix bug cũng không thêm feature
  - **`perf`**: code cải tiến về mặt hiệu năng xử lý
  - **`test`**: Những thứ liên quan đến test
  - **`vendor`**: cập nhật version cho các dependencies, packages
  - **`chore`**: những sửa đổi nhỏ nhặt không liên quan tới code như thay đổi quy trình build, tool, library

Mỗi vài commit tốt

```git
Fix bug within login screen
Refactor registration page for performance
Update validation tests for login form
Update login tests for forgotten password
Update unit tests for product search component
Merge product into main

# feat: Add new feature X

- This commit adds a new feature X to the application.
- The feature allows users to do Y and addresses the issue of Z.
- The feature was implemented using a new library W and has been thoroughly tested with a set of unit tests.
```

**[⬆ Quay trở lại đầu trang](#mục-lục-nội-dung)**
