library(readr)
library(dplyr)
library(stringr)
library(readxl)
library(usethis)


raw_lines <- read_lines("SKScomplete.txt", locale = locale(encoding = "ISO-8859-1"))

SKS_labels <- tibble(line = raw_lines) %>%
  mutate(full_code = str_match(line, "^([^ ]+)")[, 2],
         label     = str_match(line, "\\d{10,}\\s*(.*?)\\s{2,}")[, 2]) %>%
  filter(!is.na(full_code) & full_code != "") %>%
  mutate(prefix    = str_match(full_code, "^([a-z]+)([A-Z0-9]+)$")[, 2],
         proc_code = str_match(full_code, "^([a-z]+)([A-Z0-9]+)$")[, 3],
         label     = str_trim(label)) %>%
  select(Prefix=prefix, Kode=proc_code, Label=label)

patoSnoMed <- read_excel("patoSnoMed_2026-04-Komplet.xlsx")

SNOMED_labels <- patoSnoMed |>
  select(Kode = SKSkode, Label = Kodetekst)

#save(SKS_labels,    file = "SKS_labels.rda")
#save(SNOMED_labels, file = "SNOMED_labels.rda")

# 3. Save the data to data/ with xz compression
usethis::use_data(
  SKS_labels,
  compress = "xz",
  overwrite = TRUE
)

usethis::use_data(
  SNOMED_labels,
  compress = "xz",
  overwrite = TRUE
)
