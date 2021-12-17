#Chia code thành các component
1.  Base/ (chứa các setting ban đầu)
2.  Components/ ( chứa các bộ phận nhỏ dễ tái sử dụng như button, card, …)
3.  Layout/ ( chứa footer, navbar,…)
4.  Pages/ (chứa tên các page nếu project web của bạn có nhiều page khác nhau vd: home, login, ...)
5.  Abstracts/ (chứa animation, các function, mixin...)
6.  Themes/ (các mẫu có sẵn)
7.  Vendors/ (code CSS bên ngoài như bootstrap, …)

#Các thuộc tính SASS:
1.  Variables: biến dùng để tái sử dụng các giá trị cơ bản font-size, colors,...
    $tên_biến: giá trị của biến;
2.  Nesting: select và khai báo thuộc tính element con trong element cha
    .element-parent {
        font-size: 16px
        .element-child {
            color: red;
        }
    }
    .block{
  
        &__element{

            &--modifier{

            }
        }
    }
3.  Operators: cho các phép toán (+,-,*,/) vào trong code CSS
4.  Partials & Imports: viết code ở nhiều file khác nhau rồi import vào 1 file
5.  Mixins: nó giúp sử dụng lại các đoạn CSS code nhiều lần
    - Cú pháp
    @mixin tênMixin {...}
    @mixin tênMixin($variable1, $variable2,...) {...}
    - Sử dụng
    .class {
        @include tênMixin;
        @include tênMixin(value1, value2,...)
    }
6.  Functions: giống mixins nhưng có tham số
    Việc sử dụng Function trong Sass dùng để khai báo các giá trị của property với các công thức toán học (thường là chỉ sử dụng cho số đo như width, margin, padding,...)
    @function TênFunction ($variable1, $variable2, ...) {
        @return Value;
    }
7.  Extends: Kế thừa thuộc tính của các element khác trong element đang khai báo
    .example {
        float: left;
        width: 50%;
    }
    .example2 {
        @extend .example;
        background: #ffffff;
    }
8.  Control directives: viết code phức tạp hơn, sử dụng vòng lặp, điều kiện,...

#SASS có 2 loại là SASS và SCSS
1.  SASS: đuôi file .sass
    .navbar
        list-style:none
        float: left
        .navbar-list .list
            display: inline-block
            margin-left: 30px
    Không có “;”, không có “{}”, phân tách các dòng với nhau bởi khoảng thụt đầu dòng. Cách code này là cách code lúc Sass mới xuất hiện, khá phức tạp và khó để chúng ta chuyển từ CSS sang code Sass.

2.  SCSS: đuôi file .scss
    .navbar {
        list-style:none;
        float: left;
        .navbar-list .list {
            display: inline-block;
            margin-left: 30px;
        }       
    }
    Rõ ràng là dễ nhìn và dễ hiểu hơn .sass và gần giống với cách code CSS thuần.