# Grep-and-find


##1. Grep trong linux

Grep viết tắt của "Global Regular Expression Print", là lệnh tìm kiếm các dòng có chứa một chuỗi hoặc từ khóa trong file. 
**Grep** ban đầu được phát triển hệ điều hành Unix, tuy nhiên ngày nay **grep** đã được dùng trong tất cả các hệ điều hành Unix-like.

**Cú pháp lệnh**

```sh
  #grep "word" filename
  #grep " String1 string2" filename

```

- Highlight từ khóa trong kết quả bằng màu
 Đầu tiên ta phải thiết lập môi trường  ***GREP-COLOR***

```sh
 $export GREP_COLOR='kiểu_hiển_thị;màu_kí_tự;màu_nền'
 ```
 
  Bảng mã cho biến ***GREP-COLOR***
 
  <img src  = "http://i.imgur.com/Hl9htAX.png">
  
- Tìm kiếm từ trong file:
 ```sh
  # grep eth0 /etc/network/interfaces
 ```
 Nếu không nhớ chính xác là từ viết hoa hay không viết hoa thì sử dụng *-i*
   
```sh
 # grep -i eth0 /etc/network/interfaces
```
- Đếm số lần xuất hiện của từ tìm kiếm trong file:
```sh
 # grep -c eth0 /etc/network/interfaces
```
  
- Hiển thị số dòng của từ tìm kiếm trong file:
  
```sh
# grep -n eth0 /etc/network/interface
```
- Hiển thị tất cả các dòng không chứa từ tìm kiếm trong file:
 
```sh
# grep -v eth0 /etc/network/interface
 
```
- Hiển thị tất cả các dòng có từ tìm kiếm đứng đầu trong file:

```sh 
# grep ^i /etc/network/interface
 
```
 
- Hiển thị tất cả các dòng có từ tìm kiếm đứng cuối trong file:

```sh 
 # grep 1$ /etc/network/interface
```


##2. Find trong Linux

Lệnh find trong Linux được sử dụng để tìm kiếm một file, một thư mục

- Tìm tất cả các file có tên là "thom" trog toàn bộ hệ thống:
```sh
 # find / -name thom
```
  <img src = "http://i.imgur.com/g1amIgq.png">
- Tìm các file trong thư mục /**home** có owned là *thom*

```sh
 # find /home -user thom
```
  <img src = "http://i.imgur.com/Pu7Ocpe.png">
  
- Tìm các file trong thứ mục /usr có tên kết thúc là "stat"

```sh
 # find /usr -name *stat
```

  <img src = "http://i.imgur.com/2VbbaxA.png ">
  
- Tìm kiếm file theo tên không đầy đủ:

```sh
 # find /name tho*
```

<img src = "http://i.imgur.com/4ltLOyO.png">

- Tìm kiếm các file được chmod theo thông số nào đó

```sh
 #find /-perm -777
```

- Tìm các file đã được hiệu chỉnh trong vòng 24h trở lại đây trong thư mục home:

```sh
 # find $HOME -mtime 0
```
 <img src = "http://i.imgur.com/dddYGCC.png">
 
- Tìm kiếm các file trong thư mục Home đã được hiệu chỉnh trong vòng > 30 ngày trước

```sh
 # fine $HOME -mtime +30
```

 <img src = "http://i.imgur.com/FS7TQ54.png">
 
 - Tìm các file được cho phép đọc bởi tất cẩ mọi người nhưng không cho phép thực thi. 


```sh
# find / –perm –444 ! –perm /111
```
