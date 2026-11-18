Template Laporan Tugas Akhir STI STEI
Institut Teknologi Bandung

Dokumen utama:
1. TA
2. daftar-pustaka.bib
3. ta-sti.cls

by baskara at itb dot ac dot id

Petunjuk penggunaan:
1.  Ada 3 file utama, yaitu 
    - TA.tex (file utama)
    - daftar-pustaka.bib (file daftar pustaka)
    - ta-sti.cls (class file)
    Ketiga file ini harus berada di folder yang sama.
2.  Sunting TA.tex sesuai dengan kebutuhan Anda.
3.  Sunting atau generate isi daftar-pustaka.bib dengan referensi yang Anda gunakan, sesuai dengan format BibLaTeX.
4.  Kompilasi file TA.tex menggunakan XeLaTeX dan Biber (lihat urutan cara kompilasi di bawah).
5.  Hasil kompilasi adalah file TA.pdf yang siap untuk dicetak.

Eksekusi perintah-perintah berikut untuk melakukan kompilasi melalui command line (cmd atau terminal):
    1. xelatex tesis.tex
    2. biber tesis      
    3. xelatex  tesis.tex
    4. xelatex  tesis.tex

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


Catatan:
 -  Pastikan Anda telah menginstal paket-paket LaTeX yang diperlukan, termasuk
    biblatex-chicago dan fontspec.
-   Gunakan editor LaTeX yang mendukung XeLaTeX, seperti TeXstudio, Overleaf, TexShop (Mac OS) atau lainnya.

