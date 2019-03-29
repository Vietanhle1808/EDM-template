1. trong email outlook thì phải set width="100%" trực tiếp trong thẻ img thì mới nhận

img(src="https://gallery.mailchimp.com/2e20b32d492bd62d510f96468/images/6e9b7e76-f429-4b6e-9597-865d197c65bf.jpg", alt="" width="100%")
2. Table bao ngoài chứa 2 td gồm 2 nhóm elements khác nhau.
  td 1: chứa 1 table và 1 td
  td 2: chứa 1 table và 2 td
  ==> Content trong td1 sẽ tự động được set giữa và scope của nó chỉ là 1 phần nhỏ nằm giữa cả thẻ td.
  ===> thẻ "a" bao ngoài sẽ không thể cover được toàn bộ TD ngoài.
  ====> tạo thêm 2 table có height chuẩn kẹp content td 1 vào giữa 

3. Nói tiếp nếu trường hợp trên, nếu height của cả cục table trường hợp 2 không đủ thì phải set padding vào từng element trong section đó.

4. Khi ẩn images với thuộc tính hideOnPC trên outlook - Nếu trước đó là thẻ "a" thì thuộc tính này sẽ không được nhận. Khi đó chúng ta phải làm theo dạng này:

- Table bao ngoài thẻ a có chứa hideonPC nhằm đảm bảo việc trên chrome nó không hiển thị khoảng trắng.
- table phía dưới thẻ a có chứa hideonPC nhằm đảm bảo việc ẩn trên outlook.

<!-- 
table(border="0" cellpadding="0" cellspacing="0" style="max-width: 600px; width: 100%;" align="center" valign="top").hideOnPC
  tr
    td(align="center" valign="middle")
      a(href="#")
        table(align="center" valign="top" width="600" border="0" cellpadding="0" cellspacing="0" style="max-width: 600px; width: 100%;").hideOnPC
          tr
            td(align="center" valign="middle" width="100%")
              img(src="https://gallery.mailchimp.com/2e20b32d492bd62d510f96468/images/ed0bfc58-5c14-4cea-840f-d0cb28e32848.jpg", alt="img mobile" width="100%") 
-->

5. Để chỉnh màu cho text thì phải sử dụng thuộc tính <font  color="#FFFFFF"> content</font>
6. Trên outlook thì cần lưu ý đặt thẻ thuộc tính text-align cần phải đặt ở thẻ td ngay ngoài của btn.
7. tách riêng phần btn ra làm 1 components riêng biệt. Để set khoảng cách giữa 2 nút btn thì ta phải set text-center và đặt padding cho 2 btn riêng biệt. Đồng thời để structure và class tương tự nhau.
8. Lưu ý là: trên gmail app và outlook thì nhận thuộc tính giống nhau khi xét text-align ở thẻ td ngay bên ngoài button. Còn riêng với gmail trên trình duyệt thì nhận giá trị text-align ở giá trị td thứ 2 tính từ thẻ button.
9. Trong file media-responsive thì không được sử dụng biến, còn lại có thể sd bình thường.
10. thuộc tính được để trong responsive phần cho mobile thì phải để important.
11. Trong phần list car thì để không vỡ ảnh chúng ta phải đặt giá trị width % cho mỗi thứ vào trong các thẻ td bao ngoài của ảnh đó - ngoài ra phải đặt cả max-width cho ảnh img - để xử lý lỗi sát nhau của items trên mobile
12. List icon (giống trong social) thì phải sử dụng 
<!-- 
a(href="#" style="display: inline-block; padding-right:10px;").float-left
  table(border="0" cellpadding="0" cellspacing="0" style="max-width: 600px; width: 100%;" align="center" valign="top")
    tr
      td
        img(src="https://gallery.mailchimp.com/e57a2d8e3f88d8192e81cd76f/images/cdbbf08b-4857-4303-8348-78ca09d6ebb9.png", alt="facebook" width="30").social-icon 
-->