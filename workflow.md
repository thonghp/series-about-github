# Quy trình làm việc 

- B1: Tạo 1 nhánh develop.
- B2: Leader sẽ vào **Issues** trên github và giao việc cho nhân viên.

    ![alt](/assets/issue1.png)

    - **Assignees** 🠊 chỉ định người làm.
    - **Labels** 🠊 loại làm việc.
    - Khi giao xong leader sẽ submit issue lên cho các thành viên biết.
- Sau khi đã úp issue lên thì cần phải chú ý:

    ![alt](/assets/issue2.png) 

- B3: Nhân viên chỉ định sẽ tiến hành tạo nhánh để thực hiện code và nhánh có tên như sau:
    - **`git checkout -b feature/1-employee-management develop`** 🠊 tạo nhánh từ nhánh **develop** và **1** tương đương với **#1**.
- B4: Nhân viên push code nhớ là commit phải tham chiếu vào issue 🠊 **`git commit -m '#1 - code them nhan vien'`**

![alit](/assets/issue3.png)

- B5: Lúc này người review code sẽ vô tạo pull request:

    ![alt](/assets/pull-request1.png)

    - Chọn nhánh develop để pull và tạo pull.

    ![alt](/assets/pull-request2.png)

- B6: Sau khi tạo pull leader sẽ vào phần pull request để kiểm tra và merge nhánh feature vào develop.
    ![alt](/assets/pull-request3.png)    

- B7: Sau khi merge sẽ như hình sau

![alt](/assets/pull-request4.png)

- B8: sau khi merge nhân viên chuyển về nhánh develop và pull xuống.
- B9: Tạo nhánh release từ develop 🠊 **`git checkout -b release-1.0.0 develop`**.
- B10: Tạo tag trong nhánh release 🠊 **`git tag 'v1.0.0'`** sau đó push tag lên 🠊 **`git push --tags`**.

![alt](/assets/tag1.png)

![alt](/assets/tag2.png)

- B11: sau khi đã release tiến hành merge nhánh develop vào release 🠊 **`git merge develop`** sau đó push nhánh release lên remote.
- B12: review code tiến hành pull request như B5 sau đó merge nhánh release vào main.

![alt](/assets/pull-request5.png)

- B13: chuyển về nhánh main sau đó pull code xuống, tạo tag và xoá nhánh release + feature cả local và remote. 
- B14: trên nhánh main phát hiện có lỗi cần fix gấp 🠊 tạo nhánh hotfix trên main luôn 🠊 **`git checkout -b hotfixes`**.
- B15: sau khi fix xong sẽ commit tham chiếu vô đúng issue, merge vô main sau đó trở về nhánh main và pull. Sau đó xoá nhánh hotfixes

> Sẽ chỉ còn 2 nhánh là main và develop

Vd về git workflow [ở đây](https://github.com/thonghp/git-workflow-team)

