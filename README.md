#include <iostream>
using namespace std;


int main() {
    long long saldo;
    int pilihan;
    long long nominal;
    string no_rek;

    // Proses pertama: input saldo awal[cite: 5]
    cout << "Masukkan jumlah saldo awal Anda: Rp ";
    cin >> saldo;

    // Menggunakan perulangan do/while sesuai materi[cite: 4]
    do {
        cout << "\n=== MENU ATM BANK INTI ===" << endl;
        cout << "1. Informasi Saldo\n";
        cout << "2. Pengambilan Tunai\n";
        cout << "3. Pembayaran\n";
        cout << "4. Transfer\n";
        cout << "5. Keluar\n";
        cout << "Masukkan pilihan Anda : ";
        cin >> pilihan;

        switch (pilihan) {
            case 1:
                cout << "Saldo Anda saat ini: Rp " << saldo << endl; //[cite: 5]
                break;
            case 2:
                cout << "Masukkan nominal tarik tunai: Rp ";
                cin >> nominal;
                if (nominal > 2000000) {
                    cout << "Maksimal penarikan adalah Rp 2.000.000!\n"; //[cite: 5]
                } else if (nominal > saldo) {
                    cout << "Saldo tidak mencukupi!\n"; //[cite: 5]
                } else {
                    saldo -= nominal;
                    cout << "Penarikan berhasil. Sisa saldo: Rp " << saldo << endl;
                }
                break;
            case 3:
                cout << "Masukkan nominal pembayaran (Kartu Kredit/Telepon): Rp "; //[cite: 5]
                cin >> nominal;
                if (nominal > saldo) {
                    cout << "Saldo tidak mencukupi!\n"; //[cite: 5]
                } else {
                    saldo -= nominal;
                    cout << "Pembayaran berhasil. Sisa saldo: Rp " << saldo << endl;
                }
                break;
            case 4:
                cout << "Masukkan no rekening penerima: "; //[cite: 6]
                cin >> no_rek;
                cout << "Masukkan nominal transfer: Rp ";
                cin >> nominal;
                if (nominal > saldo) {
                    cout << "Saldo tidak mencukupi!\n";
                } else {
                    saldo -= nominal; //[cite: 6]
                    cout << "Transfer ke rekening " << no_rek << " berhasil. Sisa saldo: Rp " << saldo << endl;
                }
                break;
            case 5:
                cout << "Terima kasih telah menggunakan layanan kami.\n"; //[cite: 6]
                break;
            default:
                cout << "Pilihan tidak valid, silakan pilih menu 1-5.\n"; //[cite: 5]
        }
    } while (pilihan != 5); // Terus berulang sampai user pilih menu 5[cite: 5]

    return 0;
}

