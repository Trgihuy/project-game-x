# project-game-x
Đây là project game X
Bài 1
import sys
from PyQt5.QtWidgets import QApplication, QWidget, QVBoxLayout, QLineEdit, QPushButton, QLabel


class InfoApp(QWidget):
    def __init__(self):
        super().__init__()

        # Khởi tạo các widget
        self.initUI()

    def initUI(self):
        # Tạo layout chính
        layout = QVBoxLayout()

        # Tạo và thêm các widget vào layout

        self.name_input = QLineEdit()

        self.save_button = QPushButton('Hiển thị')
        # Thêm các widget vào layout

        layout.addWidget(self.name_input)
        layout.addWidget(self.save_button)
        self.display_label = QLabel('Tên của bạn là: ')
        layout.addWidget(self.display_label)

        # Thiết lập layout cho widget chính
        self.setLayout(layout)
        # Kết nối các nút với các phương thức xử lý
        self.save_button.clicked.connect(self.save_info)
        # Thiết lập tiêu đề và kích thước cửa sổ
        self.setWindowTitle('Hiển thị tên')
        self.setGeometry(100, 100, 300, 250)
    def save_info(self):
        # Lấy thông tin từ các trường nhập liệu
        name = self.name_input.text()

        # Cập nhật QLabel với thông tin đã nhập
        self.display_label.setText(f'Họ tên: {name}')
if __name__ == '__main__':
    app = QApplication(sys.argv)
    ex = InfoApp()
    ex.show()
    sys.exit(app.exec_())