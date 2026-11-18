Template Laporan Tugas Akhir STI STEI
Institut Teknologi Bandung

Dokumen utama:
1. TA
2. daftar-pustaka.bib
3. ta-sti.cls

by baskara at itb dot ac dot id

**Petunjuk Umum**
1.  Ada 3 file utama, yaitu 
    - TA.tex (file utama)
    - daftar-pustaka.bib (file daftar pustaka)
    - ta-sti.cls (class file)
    Ketiga file ini harus berada di folder yang sama.
2.  Sunting TA.tex sesuai dengan kebutuhan Anda.
3.  Sunting atau generate isi daftar-pustaka.bib dengan referensi yang Anda gunakan, sesuai dengan format BibLaTeX.
4.  Kompilasi file TA.tex menggunakan XeLaTeX dan Biber (lihat urutan cara kompilasi di bawah).
5.  Hasil kompilasi adalah file TA.pdf yang siap untuk dicetak.

**Compiler**
Secara umum, *compiler* dapat diunduh dari https://www.tug.org/texlive/. Namun, beberapa pengembang telah mengemas *installer* untuk berbagai sistem operasi yang memudahkan kita dalam instalasi. 
1. Mac OS: MacTeX (https://tug.org/mactex/mactex-download.html).
2. Windows: Miktex (https://miktex.org/download). Pilih All Downloads, kemudian pilih Net Installer untuk mengunduh semua paket.
3. Linux: texlive (gunakan *installer* di distro masing-masing, misalnya *apt* di Ubuntu).

**Text Editor**
Secara umum, semua penyunting teks dapat digunakan, asalkan berkas disimpan dalam format *plaintext*, bukan *richtext*. 
Namun, ada beberapa perangkat lunak yang direkomendasikan untuk digunakan karena dapat diintegrasikan dengan *compiler* (IDE).
Beberapa di antaranya dapat dilihat di https://www.typetex.app/best-latex-editors-2026.
Khusus pengguna Mac OS, direkomendasikan menggunakan VS Code, TexShop, atau Lattice (Newcomer, Free, https://leo1oel.github.io/lattice/).

**Kompilasi menggunakan Terminal atau CMD**
Eksekusi perintah-perintah berikut untuk melakukan kompilasi melalui command line (cmd atau terminal):
1. xelatex TA.tex
2. biber TA
3. xelatex  TA.tex
4. xelatex  TA.tex

**Kompilasi menggunakan Visual Studio Code**
Jika meenggunakan Visual Studio Code sebagai editor, pastikan menambahkan "latex-workshop.latex.tools" dan
    "latex-workshop.latex.recipes" di bawah ini di JSON User Settings:

"latex-workshop.latex.tools": [ 
       {
           "name": "xelatex",
           "command": "xelatex",
           "args": [
               "-synctex=1",
               "-interaction=nonstopmode",
               "-file-line-error",
               "%DOC%"
           ]
       },
       {
           "name": "biber",
           "command": "biber",
           "args": [
               "%DOCFILE%"
           ]
       }
   ],
   "latex-workshop.latex.recipes": [
       {
           "name": "xelatex -> biber -> xelatex*2",
           "tools": [
               "xelatex",
               "biber",
               "xelatex",
               "xelatex"
           ]
       }
   ]




