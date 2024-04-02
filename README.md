#include<stdio.h>
#include<stdlib.h>
#include<math.h>
#include<string.h>
#include<time.h>
#include<stdbool.h>

// Khai báo các hàm
void nhapTienHocPhi();
void nhapDanhSachSinhVien();
void nhapDiaChiSinhVien();

int main() {
    int choice;

    // Hiển thị Menu
    printf("Menu:\n");
    printf("1. Tien hoc phi cua sinh vien\n");
    printf("2. Danh sach sinh vien\n");
    printf("3. Dia chi sinh vien\n");
    printf("4. Thoat\n");
    printf("Lua chon 1 trong 4: ");
    scanf("%d", &choice);

    // Xử lý lựa chọn
    switch(choice) {
        case 1:
            printf("Tien hoc phi cua sinh vien.\n");
            nhapTienHocPhi();
            break;
        case 2:
            printf("Danh sach sinh vien.\n");
            nhapDanhSachSinhVien();
            break;
        case 3:
            printf("Dia chi sinh vien.\n");
            nhapDiaChiSinhVien();
            break;
        case 4:
            printf("Ban co chac chan muon thoat.\n");
            printf("yes or no");
            break;
        default:
            printf("Lua chon khong hop le.\n");
            break;
    }

    return 0;
}

void nhapTienHocPhi() {
    float hocPhiThang1, hocPhiThang2;

    // Nhập thông tin về tiền học phí cho tháng 1
    printf("Nhap tien hoc phi cho thang 1: ");
    scanf("%f", &hocPhiThang1);

    // Nhập thông tin về tiền học phí cho tháng 2
    printf("Nhap tien hoc phi cho thang 2: ");
    scanf("%f", &hocPhiThang2);

    // Hiển thị thông tin về tiền học phí đã nhập
    printf("Tien hoc phi cho thang 1: %.2f\n", hocPhiThang1);
    printf("Tien hoc phi cho thang 2: %.2f\n", hocPhiThang2);
}

void nhapDanhSachSinhVien() {
    struct SinhVien {
        char ten[50];
        float hocPhiThang1;
        float hocPhiThang2;
    };
    int soLuongSinhVien;

    // Nhập số lượng sinh viên
    printf("Nhap so luong sinh vien: ");
    scanf("%d", &soLuongSinhVien);

    // Khai báo mảng cấu trúc cho sinh viên
    struct SinhVien danhSachSinhVien[soLuongSinhVien];

    // Nhập thông tin của từng sinh viên từ bàn phím
    for (int i = 0; i < soLuongSinhVien; i++) {
        printf("\nNhap thong tin cho sinh vien thu %d:\n", i + 1);
        printf("Nhap ten: ");
        scanf("%s", danhSachSinhVien[i].ten);
        printf("Nhap hoc phi thang 1: ");
        scanf("%f", &danhSachSinhVien[i].hocPhiThang1);
        printf("Nhap hoc phi thang 2: ");
        scanf("%f", &danhSachSinhVien[i].hocPhiThang2);
    }

    // Hiển thị thông tin của từng sinh viên
    printf("\nThong tin danh sach sinh vien:\n");
    for (int i = 0; i < soLuongSinhVien; i++) {
        printf("Sinh vien thu %d\n", i + 1);
        printf("Ten: %s\n", danhSachSinhVien[i].ten);
        printf("Hoc phi thang 1: %.2f\n", danhSachSinhVien[i].hocPhiThang1);
        printf("Hoc phi thang 2: %.2f\n", danhSachSinhVien[i].hocPhiThang2);
    }
}

void nhapDiaChiSinhVien() {
    struct Diachi {
        float sonha;
        float soduong;
        char tenquan[20];
        char cityname[20];
    };
    struct Diachi diachiSV;
    printf("nhap so nha(float): ");
    scanf("%f", &diachiSV.sonha);
    printf("nhap so duong(float): ");
    scanf("%f", &diachiSV.soduong);
    printf("nhap ten quan(char): ");
    scanf("%s", diachiSV.tenquan);
    printf("nhap cityname(char): ");
    scanf("%s", diachiSV.cityname);
    printf("\nThong tin dia chi sinh vien:\n");
    printf("so nha: %.2f\n", diachiSV.sonha);
    printf("so duong: %.2f\n", diachiSV.soduong);
    printf("ten quan: %s\n", diachiSV.tenquan);
    printf("cityname: %s\n", diachiSV.cityname);
}
