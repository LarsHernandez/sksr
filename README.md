
<!-- README.md is generated from README.Rmd. Please edit that file -->

# sksr - SKS labels i R

[![CRAN_Status_Badge](https://www.r-pkg.org/badges/version/sksr)](https://cran.r-project.org/package=sksr)

Hovedfunktionen for sksr er at give labels til danske SKS koder. Koderne
er fra Sundhedsdatastyrelsen
[sundhedsdata.dk](https://filer.sundhedsdata.dk/sks/data/skscomplete/)
og er med versionen opdateret: 16-06-2026

## SNOMED koder

SKS systemet inkluderer nogle SNOMED koder, der er dog inkluderet det
fulde sæt fra …

## Installation

sksr kan installeres fra github med kode

``` r
pak::pkg_install("LarsHernandez/sksr")
```

# Data

``` r
head(SKS_labels)
#>   Prefix  Kode                           Label
#> 1    adm     A          Administrative forhold
#> 2    adm    AA   Patientadministrative forhold
#> 3    adm   AAF                         Booking
#> 4    adm  AAF1                     Indlæggelse
#> 5    adm AAF11                  Genindlæggelse
#> 6    adm AAF12 Indlæggelse i brugerstyret seng
```

``` r
head(SNOMED_labels)
#>     Kode                                Label
#> 1 EYYY00 udgået (forkert oprettet, se ÆYYY00)
#> 2 F00150                              kakeksi
#> 3 F01050                postoperativ tilstand
#> 4 F01051            komplet mesorektal fascie
#> 5 F01051                     mesorektalt plan
#> 6 F01051           mesorektalt resektionsplan
```

## References

Indeholder data fra Sundhedsdatastyrelsen fra …
