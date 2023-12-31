**TRƯỜNG ĐẠI HỌC SƯ PHẠM KỸ THUẬT THÀNH PHỐ HỒ CHÍ MINH**
**NHÓM 06:** 
KIẾN ĐỨC TRỌNG: 21110332 
PHẠM QUỐC TRUNG: 21110335 

Đề tài: **XÂY DỰNG ỨNG DỤNG TRÌNH DUYỆT WEB** 
Môn: **CẤU TRÚC DỮ LIỆU VÀ GIẢI THUẬT**

**MỤC LỤC** 
[**LỜI NÓI ĐẦU**.............................................................................................................. 1 ](#_page1_x204.00_y656.92)
[**PHẦN NỘI DUNG** ...................................................................................................... 2 ](#_page3_x54.00_y56.92)
1. [**Danh sách liên kết đôi (Doubly Linked List) và định nghĩa của một tab** ..... 2 ](#_page3_x54.00_y74.92)
1. [**Danh sách liên kết đôi** ................................................................................. 2 ](#_page3_x90.00_y103.92)
1. [**Tab Group** .................................................................................................... 2 ](#_page3_x54.00_y366.92)
1. [**Biến toàn cục** ................................................................................................ 2 ](#_page3_x90.00_y558.92)
2. [**Thao tác thực hiện trên một tab** ....................................................................... 3 ](#_page4_x54.00_y56.92)
1. [**Access Website** ............................................................................................. 3 ](#_page4_x54.00_y629.92)
2. [**Open New Tab và Open Tab List** .............................................................. 4 ](#_page5_x54.00_y293.92)
3. [**Chức năng thêm tab vào group** ......................................................................... 4 ](#_page5_x54.00_y548.92)
1. [**Add This Tab To Group** ............................................................................. 5 ](#_page6_x54.00_y101.92)
1. [**Open Group** ................................................................................................. 6 ](#_page7_x54.00_y56.92)
1. [**Close Group/Tab và Open Closed Tab/Group** ......................................... 6 ](#_page7_x54.00_y271.92)
4. [**Chức năng lưu lịch sử (History)** ........................................................................ 7 ](#_page8_x54.00_y56.92)
1. [**Search Histoy** ............................................................................................... 7 ](#_page8_x90.00_y324.92)
1. [**Truy cập vào địa chỉ và Xóa địa chỉ lịch sử cụ thể** ................................... 7 ](#_page8_x90.00_y585.92)
5. [**Chức năng lưu dấu trang (Bookmark)** ............................................................. 8 ](#_page9_x54.00_y56.92)
1. [**Open Bookmark Address** ........................................................................... 9 ](#_page10_x54.00_y56.92)
1. [**Open Folder** ............................................................................................... 10 ](#_page11_x54.00_y56.92)

<a name="_page1_x204.00_y656.92"></a>**LỜI NÓI ĐẦU** 

Ở bài đồ án này, chúng tôi lựa chọn thực hiện xây dựng chương trình trình duyệt web dựa trên các kỹ thuật cơ bản được ứng dụng từ “danh sách liên kết đôi”. Chức năng chính của chương trình là các thao tác truy cập trang web, danh sách liên kết có thể trỏ đến next và back để chuyển trang hiện hành trên màn hình, được thực hiện trên từng tab. Ngoài ra, còn có các chức năng cơ bản khác của một trình duyệt như: 

- Mở tab mới và quản lý các tab; 
- Nhóm các tab lại thành từng các group cụ thể, các thao tác di chuyển các tab qua lại của các group khác nhau; 
- Thao tác đóng tab và đóng một group có nhiều tab. 
- Ứng dụng stack để lưu lại các tab hoặc các group đã đóng và có thể thao tác mở lại các tab đó hoặc mở lại một group chứa nhiều tab; 
- Lưu lịch sử của các trang web đã duyệt và các thao tác tìm kiếm, thêm, xóa của danh sách lịch sử; 
- Chức năng thực hiện lưu các địa chỉ trang web cụ thể vào bookmark, tạo folder bookmark chứa nhiều địa chỉ và có các thao tác cơ bản như xóa địa chỉ, xóa folder, di chuyển địa chỉ từ folder này sang folder khác, Unfolder (bung các địa của một folder ra danh sách bookmark bên ngoài). 

<a name="_page3_x54.00_y56.92"></a>**PHẦN NỘI DUNG** 

1. **Danh<a name="_page3_x54.00_y74.92"></a> sách liên kết đôi (Doubly Linked List) và định nghĩa của một tab** 
1. **Danh<a name="_page3_x90.00_y103.92"></a> sách liên kết đôi** 

Một node trong list chứa địa chỉ duyệt web và hai node trỏ next và back, chức năng dùng để trỏ tới trang tiếp và trang trước đó. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.004.png) ![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.005.png)

Một list được coi là một tab, được định nghĩa bao gồm ba node trỏ: node head và tail quản lý vị trí đầu và vị trí cuối, node present trỏ tới trang hiện hành để nhận biết thông tin của vị trí trang web đang được sử dụng; và biến pos để nhận biết vị trí của tab đó trong một group tab. 

2. **Tab<a name="_page3_x54.00_y366.92"></a> Group** 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.006.png)

Một tab group chứa nhiều tab (các list được định nghĩa là tab), biến nTG chỉ số lượng tab trong một group , và có tên group, biến pos chỉ vị trí của group đó trong danh sách tab toàn cục của một trình duyệt. 

3. **Biến<a name="_page3_x90.00_y558.92"></a> toàn cục** 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.007.png)![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.008.png)

Biến toàn cục chứa tất cả các group tab của chương trình là mảng một chiều chứa các tabgroup và nTL là số lượng group tương ứng. Ngoài ra, còn có các biến toàn cục khác như mảng history[] và nH chứa lần lượt là các địa chỉ được lưu vào lịch sử và số lượng địa chỉ, tương tự bookmark[] và nBM lần lượt là mảng chứa số lượng địa chỉ được lưu vào dấu trang và số lượng dấu trang. 

2. **Thao<a name="_page4_x54.00_y56.92"></a> tác thực hiện trên một tab** 

Khi chạy chương trình, thực hiện hàm OpenNewTab, tạo ra một group, một list và một node. Địa chỉ khởi tạo của node (trang web) là “New Tab” và thêm node đó vào cuối list, tiếp tục thêm list vào group và cuối cùng là thêm group vào tablist (biến toàn cục chứa danh sách group). 

Sau dó, thực hiện chiếu lên màn hình tab đó, đưa vào các biến lần lượt là TabGroup g (group chứa list), LLIST l (list hiện hành của một tab), Node p (vị trí trang hiện tại của một tab – node present của list). 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.009.jpeg)

Giao diện hiện lên màn hình Console gồm địa chỉ trang web hiện tại và các số của lần lượt các chức năng cho phép thao tác. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.010.jpeg)

1. **Access<a name="_page4_x54.00_y629.92"></a> Website** 

Đầu tiên là option số 1, thực hiện nhập vào tên địa chỉ của một trang web và list sẽ trỏ đến node chứa địa chỉ của trang web đó và màn hình sẽ hiện thao tác được cho phép trong node đó. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.011.jpeg) ![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.012.jpeg)

Khi hiện hành các trang đang được thao tác thì màn hình sẽ hiện những thao tác được cho phép Next và Back tùy thuộc vào node next và node back của trang đó có tồn tại hay không. 

2. **Open<a name="_page5_x54.00_y293.92"></a> New Tab và Open Tab List** 

Tiếp theo là option số 2, chức năng mở lên một tab mới, tương tự tab mới cũng có tên địa chỉ là New Tab và có các chức năng thao tác, giao diện giống hệt tab đầu tiên. 

Để quản lý và chuyển đổi giữa các tab, ta chọn số 4, thực hiện mở danh sách các tab đã được tạo. Tên của từng tab sẽ được hiện theo tên địa chỉ hiện hành gần nhất của nó. Nếu là group thì sẽ hiện groupname của tab group đó. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.013.png)![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.014.png)

3. **Chức<a name="_page5_x54.00_y548.92"></a> năng thêm tab vào group** 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.015.png) ![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.016.png)

Để thuận tiện cho tính năng thêm tab vào group thì một tab được định nghĩa là một group chứa duy nhất một list và tên group là rỗng (“\0”). Khi thêm một tab mới thì tab đó được đưa vào một group và group đó được thêm vào danh sách tab group toàn cục. Và khi thực hiện tạo một group từ một tab cụ thể nào đó, ta đổi tên group chứa tab đó từ rỗng (“\0”) sang một tên mới, group đó sẽ được định nghĩa là một group chứa một tab. Hàm kiểm tra group đó là một tab hay là một group tab sẽ kiểm tra groupname của tab đó có khác rỗng hay không. 

1. **Add<a name="_page6_x54.00_y101.92"></a> This Tab To Group** 

Khi lựa chọn “Add This Tab To Group” (Option thứ 3 của tab), màn hình sẽ hiện ra các bảng thao tác các chức năng. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.017.png)

Nếu tab đó chưa được thêm vào group nào thì có hai thao tác, một là thêm vào một group mới (Add this Tab to New Group), hai là di chuyển tab đó vào một group có sẵn (nếu có group đã tạo trước đó) (Move this Tab to available Group). Khi chọn tạo group mới sẽ nhập tên group. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.018.jpeg)

Nếu tab đó đã được thêm vào group rồi thì có hai thao tác, một là đưa tab đó ra khỏi group (nếu còn một tab trong group thì group sẽ bị xóa (ungroup)), hai là đưa tab đó vào một group đã được tạo trước đó. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.019.png)

Khi chọn “Move this Tab to available Group”, màn hình sẽ hiện ra danh sách các group đã được tạo và người dùng chọn một trong số đó. 

2. **Open<a name="_page7_x54.00_y56.92"></a> Group** 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.020.jpeg)

Khi mở một group, giao diện đưa ra các thao tác như: Chọn một trong số tab có trong group để truy cập đến tab đó; Đổi tên group; Đóng group (Group được đóng sẽ được đẩy vào stack); và Trở lại danh sách các tab. 

3. **Close<a name="_page7_x54.00_y271.92"></a> Group/Tab và Open Closed Tab/Group** 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.021.jpeg) ![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.022.png)

Nếu lựa chọn “Close Tab”, màn hình sẽ quay về danh sách tab và có thêm một chức năng mới là “Open Closed Group”, có thể thực hiện thêm lại group đã được đóng. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.023.jpeg)![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.024.jpeg)

Tương tự, khi thực hiện chức năng số 7 “Close this Tab” ở một tab cụ thể thì trong danh sách tab sẽ có chức năng “Open Closed Tab” – mở lại tab đã đóng. Nếu chỉ còn một tab thì sau khi đóng tab, chương trình sẽ thực hiện Exit – thoát khỏi chương trình. 

4. **Chức<a name="_page8_x54.00_y56.92"></a> năng lưu lịch sử (History)** 

Mỗi lần thực hiện truy cập vào một trang web, lịch sử sẽ được đọc và ghi vào file text. Và mỗi lần khởi chạy, chương trình sẽ đọc file từ file text chứa danh sách chứa lịch sử và lưu vào mảng. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.025.png) ![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.026.png)

Khi mở danh sách lịch sử (Option thứ 5 của tab) sẽ có các chức năng như: Tìm kiếm lịch sử; Xóa tất cả địa chỉ của lịch sử; và Chọn địa chỉ cụ thể. 

1. **Search<a name="_page8_x90.00_y324.92"></a> Histoy** 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.027.png) ![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.028.jpeg)

Khi thực hiện thao tác tìm kiếm lịch sử, nhập vào từ khóa và chương trình sẽ hiển thị ra các kết quả có địa chỉ chứa các từ khóa đó. Nếu không có từ khóa nào, xuất dòng chữ “No Search results”. Và ta có thể tìm kiếm lại nhiều lần bằng cách lựa chọn option “Search again”. 

2. **Truy<a name="_page8_x90.00_y585.92"></a> cập vào địa chỉ và Xóa địa chỉ lịch sử cụ thể** 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.029.png)

Khi thực hiện lựa chọn một địa chỉ lịch sử cụ thể sẽ có hai thao tác, một là truy cập vào địa chỉ đó, hai là xóa địa chỉ đó khỏi lịch sử. 

5. **Chức<a name="_page9_x54.00_y56.92"></a> năng lưu dấu trang (Bookmark)** 

Tương tự như lịch sử duyệt web, bookmark cũng được khởi tạo và đọc từ file text các dữ liệu được lưu trước đó khi khởi chạy chương trình. Bookmark dùng để đánh dấu trang và có thể truy cập lại vào trang đó, có thể phân thành từng folder chứa các nhóm địa chỉ cụ thể. Lưu ý, nếu trang hiện hành là “New Tab” thì không thể bookmark. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.030.png) ![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.031.png)

Khi lựa chọn “Bookmark Controller” (Option thứ 6 của tab), giao diện Console sẽ chiếu ra các option như: “Show Bookmark Manager” là mở danh sách các dấu trang đã được bookmark; và “Bookmark this Tab” là để lưu địa chỉ tab hiện hành vào danh sách bookmark (biến toàn cục). Vì trang hiện hành là “New Tab” không thể được bookmark nên sẽ chỉ có hai option là chiếu danh sách bookmark và quay trở lại tab. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.032.jpeg)

Khi lựa chọn option “Show Bookmark Manager”, màn hình sẽ chiếu ra danh sách các lựa chọn địa của của bookmark và các folder chứa địa chỉ bookmark. Ta cũng có thể lựa chọn option “Bookmark current Tab”, để mark địa chỉ hiện hành vào danh sách bookmark (đối với trang không phải là “New Tab”). 

1. **Open<a name="_page10_x54.00_y56.92"></a> Bookmark Address** 

Khi chọn một địa chỉ cụ thể, trong có có các thao tác được cho phép như truy cập vào địa chỉ, xóa địa chỉ khỏi bookmark, thêm địa chỉ này vào một folder mới, và di chuyển địa chỉ này tới folder đã có sẵn (nếu có). 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.033.jpeg)

Tương tự như group của các tab, khi thêm vào một folder mới, ta nhập vào foldername của folder, sau đó màn hình console chiếu lại danh sách bookmark. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.034.jpeg)

Còn khi thực hiện di chuyển di chuyển sang một folder khác, màn hình sẽ chiếu ra các folder có sẵn và ta lựa chọn một trong số các folder đó để lưu địa chỉ bookmark. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.035.jpeg)

2. **Open<a name="_page11_x54.00_y56.92"></a> Folder** 

Khi lựa chọn mở một folder, màn hình sẽ chiếu ra danh sách các địa chỉ nằm trong folder đó. Có các option như bookmark địa chỉ của tab hiện hành vào folder này (trừ trường hợp nếu là New Tab sẽ không có option này), thay đổi tên folder, unfolder – đưa tất cả các địa chỉ trong folder ra bên ngoài danh sách bookmark. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.036.jpeg)

Khi thực hiện option “Unfolder”, tất cả các địa chỉ nằm trong folder đó sẽ được bung ra ngoài danh sách bookmark. 

![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.037.jpeg)![](/images/Aspose.Words.a2a54b18-6ff9-4dae-9df7-5c962fc3336b.038.jpeg)
11 
