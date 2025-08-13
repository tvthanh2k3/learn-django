### Notes

# python -m pip install --upgrade pip

-   Dùng Python để chạy Module pip và nâng cấp pip lên phiên bản mới nhất.

# mkdir django_project

-   mkdir = make directory, tạo một thư mục mới tên django_project.
-   Đây sẽ là thư mục gốc chứa dự án.

# cd django_project

-   cd = change directory, di chuyển vào thư mục django_project.

# python -m venv myproject

-   Tạo môi trường ảo tên myproject bằng module venv.
-   Giúp tách biệt thư viện của dự án này với các dự án khác.

# venv\Scripts\activate

-   Kích hoạt môi trường ảo (trên Windows).
-   Sau khi kích hoạt, mọi lệnh pip install sẽ cài vào môi trường này, không ảnh hưởng toàn hệ thống (Nếu thư mục môi trường bạn đặt tên myproject thì lệnh sẽ là myproject\Scripts\activate).

# pip install Django

-   Cài framework Django vào môi trường ảo hiện tại.

# django-admin --version

-   Kiểm tra phiên bản Django đã cài.

# django-admin startproject test_project

-   Tạo một dự án Django mới tên test_project.
-   Django sẽ sinh ra cấu trúc thư mục mặc định: manage.py và thư mục test_project/ chứa cài đặt dự án.

# ls test_project

-   ls (list) = liệt kê các file và thư mục bên trong test_project.
-   Trên Windows, tương đương dir.

# python manage.py runserver

-   Chạy máy chủ phát triển (development server) của Django.
-   Mặc định lắng nghe tại http://127.0.0.1:8000/.

# django-admin startapp test_app

-   Tạo một ứng dụng Django mới tên test_app bên trong dự án.
-   Mỗi “app” trong Django thường đảm nhiệm một chức năng (blog, user, sản phẩm...).

# pip freeze

-   Liệt kê tất cả gói đã cài + phiên bản (django==5.0.7).

# pip freeze > requirements.txt

-   Xuất danh sách tất cả các thư viện Python đang cài trong môi trường hiện tại (kèm phiên bản) vào file requirements.txt.

# pip install -r requirements.txt

-   Dùng để cài đặt toàn bộ thư viện và đúng phiên bản được liệt kê trong file requirements.txt.

# python manage.py migrate

-   Dùng để áp dụng các thay đổi cơ sở dữ liệu (database schema) dựa trên các file migration của Django

# python manage.py makemigration

-   Dùng để tạo file migration mô tả các thay đổi bạn vừa làm với models.

# python manage.py createsuperuser

-   Dùng để tạo một tài khoản quản trị (superuser) cho hệ thống.

# python manage.py shell

-   Mở ra một môi trường Python tương tác nhưng có tích hợp toàn bộ Django project của bạn
-   Nói cách khác, nó giống python trong terminal, nhưng:

*   Django đã được load sẵn (settings, models, database connection...).
*   Bạn có thể import và làm việc với model, query database ngay lập tức

-   Ví dụ:

*   from leads.models import User, Lead

*   Tạo user - u = User.objects.create(username="john", password="123456")

*   Tạo lead - Lead.objects.create(first_name="Alice", last_name="Nguyen", age=25, agent_id=1)

*   Lấy dữ liệu - Lead.objects.all()
