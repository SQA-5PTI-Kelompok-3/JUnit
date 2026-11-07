# JUnit SQA

KELOMPOK 3

Proyek contoh unit testing menggunakan **JUnit 5 (JUnit Jupiter)** pada sebuah aplikasi kalkulator sederhana, dibuat untuk kebutuhan mata kuliah / praktikum Software Quality Assurance (SQA).

## Teknologi

- Java 25
- Maven
- JUnit Jupiter 6.1.3
- Maven Surefire Plugin 3.5.4

## Struktur Proyek

```
junit-sqa/
├── pom.xml
└── src
    ├── main/java/org/calculator
    │   ├── Calculator.java   # Kelas kalkulator yang diuji
    │   └── Main.java
    └── test/java/org/calculator
        └── CalculatorTest.java  # Unit test untuk Calculator
```

## Kelas yang Diuji: `Calculator`

Fungsi yang tersedia:

| Metode | Deskripsi |
| --- | --- |
| `add(int a, int b)` | Menjumlahkan dua bilangan bulat |
| `subtract(int a, int b)` | Mengurangkan dua bilangan bulat |
| `multiply(int a, int b)` | Mengalikan dua bilangan bulat |
| `divide(double a, double b)` | Membagi dua bilangan; melempar `ArithmeticException` jika pembagi adalah 0 |

## Menjalankan Pengujian

```bash
mvn test
```

Setelah dijalankan, laporan hasil test akan tersedia di `target/surefire-reports/`.

## Kasus Uji

`CalculatorTest` mencakup:

- `testAddition` — memverifikasi `add(5, 3) == 8`
- `testSubtraction` — memverifikasi `subtract(5, 3) == 2`
- `testMultiplication` — memverifikasi `multiply(5, 3) == 15`
- `testDivision` — memverifikasi `divide(6, 3) == 2.0`
- `testDivisionByZero` — memverifikasi `divide(10, 0)` melempar `ArithmeticException`
