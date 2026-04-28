arsitektur MiniOS, **modul kernel** merujuk pada sebuah file modul berformat SquashFS (berekstensi `.sb`) yang secara spesifik bernama **01-kernel.sb**.

Modul `01-kernel.sb` ini berfungsi untuk menampung **kernel Linux beserta driver-driver perangkat keras**. Sistem MiniOS akan memuat modul ini berdasarkan nomor urutannya ("01") sebagai lapisan _read-only_ (hanya-baca) dan bertindak sebagai lapisan fondasi utama sebelum modul-modul lainnya—seperti firmware, komponen antarmuka grafis, lingkungan desktop, dan aplikasi—dimuat di atasnya

"modul kernel" (atau _Loadable Kernel Module_ / LKM) biasanya merujuk pada potongan kode perangkat lunak (seperti driver hardware tertentu) yang dapat ditambahkan (dimuat) atau dihapus dari kernel utama yang sedang berjalan secara dinamis tanpa mengharuskan Anda untuk melakukan _reboot_ sistem. Namun, dalam dokumentasi Anda, istilah ini secara praktis digunakan untuk menyebut paket _file_ `.sb` yang menyimpan seluruh inti kernel Linux tersebut pada distribusi MiniOS.

### Modular System

**SquashFS Modules (.sb):**

- **01-kernel.sb:** Linux kernel and drivers.
- **02-firmware.sb:** Firmware for hardware.
- **03-gui-base.sb:** Basic graphical interface components.
- **04-desktop.sb:** Desktop environment.
- **05-apps.sb:** Application suite.

**Module Loading:**

- Modules are loaded in order of their numbering.
- Each module is mounted as a "read-only" layer.
- Modules with a higher number can override files from modules with a lower number.