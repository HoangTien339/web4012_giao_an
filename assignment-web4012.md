## 1. Thời hạn nộp assignment
- 12/10/2019: chấm assignment 1: phần 1,2,3,4,5
- 22/10/2019: chấm assignment 2: phần 6,7


## 2. Nội dung bài assignment
1. CRUD 4 bảng
2. Migration/Seeder/Model đầy đủ
3. Route

    3.1. name, get/post, redirect, params

    3.2. group, prefix
4. MVC
5. Layout cho từng phần giao diện
6. Validate
7. Auth + Middleware

### Mô tả chi tiết
- Xây dựng 1 blog:
    - users: người dùng đăng bài(role 1), admin quản lí (role 2). user thường có thể  bị block bởi admin -> inactive
    - posts: bài đăng được đăng bởi người dùng. bài post phải thuộc 1 category nào đó.
    - comments: comments cần thuộc 1 bài đăng nào đấy. comment có thể bị inactive bởi admin (vd: comment không phù hợp ...)
    - categories: danh mục 1 cấp. cần có thông tin về người tạo (chỉ admin mới có quyền tạo)

- Đối với admin: cần đủ 4 màn hình quản lí user/post/comment/category, và đủ 4 chức năng CRUD.
- Đối với user thường: có màn hình:
    - R/U profile cá nhân
    - xem toàn bộ các bài đăng của người khác
    - xem toàn bộ bài đăng cá nhân + comment của người khác

## 3. Chi tiết các bảng
- users
    - tên
    - ngày sinh
    - sdt
    - email
    - password
    - role: 1,2 ~ user/admin
    - is_active: true/false
- posts:
    - title
    - content
    - timestamp (sử dụng laravel timestamp)
    - thuộc danh mục nào (category_id)
    - người đăng: user_id
- comments
    - thuộc bài đăng nào (post_id)
    - content
    - người đăng (user_id)
    - is_active: true/false
- categories
    - người tạo (user_id)
    - tên
## 4. Note - Convention
   - Các bảng cần được đặt tên theo chuẩn Laravel: tên tiếng anh, viết thường, số nhiều. ex: posts, users, categories ...
   - Tất cả các bảng đều cần timestamp của Laravel
   - Khóa chính trong bảng đặt là `id`.
   - Khóa ngoại đặt theo convention: `user_id`, `post_id`, ...
