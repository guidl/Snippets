# PdfTK

Commandes à lancer dans un shell powershell

Pour extraire les pages 5 -8 dans un autre pdf
```$ pdftk 20220323_NP_COMLOG_24RI_CDC_333_PV.pdf cat 5-8 output extract.pdf```

Pour tourner le pdf vers la gauche 
```$ pdftk extract.pdf cat 1-endwest output rotate.pdf```

Un quart de tour vers la droite à partir de la page 2
```$ pdftk toto.pdf cat 2-endnorth output rotate.pdf```
ou plutôt
```$ pdftk .\autorisation.PDF  cat 1-endeast output autorisation_rotated.pdf```

Merge 
```$ pdftk file1.pdf file2.pdf cat output mergedfile.pdf```

## useful links
https://www.pdflabs.com/docs/pdftk-man-page/#dest-operation
