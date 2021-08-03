# Compress a PDF
[src](https://askubuntu.com/questions/207447/how-to-reduce-the-size-of-a-pdf-file)

```
gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/default \
    -dNOPAUSE -dQUIET -dBATCH -dDetectDuplicateImages \
    -dCompressFonts=true -r150 -sOutputFile=output.pdf input.pdf
```
