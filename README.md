# 108-2-78-inclass-practice
---
 title: "Untitled"
 author: "ting" 
 date: "3/25/2020""
 output: "html_document"
---

library(googlesheets4)
install.packages(c("googlesheets4","tidyverse"))

```{r setup,include=FALSE }
knitr::opts_chunk$set(echo = TRUE)
```

```{r}
library(lubridate)
tpeTime <- ymd_hms("2020-03-18 13:52:40",
        tz="Asia/Taipei")
        tpeTime
```        





