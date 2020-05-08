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
#04-06

```{r}
vectorExample <-c(2,6,7 )
listexample  <- list(2,6,7 )

vectorExample
listexample

```


# list?t????lists, ?l?hlist?S?U?t????vectors
```{r}
`?p??108?Ǧ~?Ҫ?C` <- list(
  `108?Ǧ~??1?Ǵ?`=list(
    c("108-1"), # ?i?u?g "108-1"
    c("???ŷ|?p??","?????έp??")
       ),
  `108?Ǧ~??2?Ǵ?`=list(
    c("108-2"),
    c("???b?ԤB???w")
  )
)
print(`?p??108?Ǧ~?Ҫ?C`)
```


```{r}
# list?t????lists, ?l?hlist?S?U?t????vectors
"?p??108?Ǧ~?Ҫ?C" <- list(
  `108?Ǧ~??1?Ǵ?`=list(
    "108-1", # ?i?u?g "108-1"
    'course'=c("???ŷ|?p??","?????έp??")
       ),
  `108?Ǧ~??2?Ǵ?`=list(
    c("108-2"),
    c("???b?ԤB???w")
  )
)
print(`?p??108?Ǧ~?Ҫ?C`)
```

```{r}
commit <- list(
  author = c("Martin?Ѯv", "mtlin@gm.ntpu.edu.tw", "2020-03-25T07:17:40Z"),
  committer = c("emilyluckey", "emily007@gmail.com", "2020-03-26T08:18:40Z"),
  message = c("update")
)
print(commit)
```

```{r}
library(lubridate)
authorValues <- 
  list(
    name="Martin?Ѯv",  
    email="mtlin@gm.ntpu.edu.tw",
    time=ymd_hms("2020-03-25T07:17:40Z")
  )
committerValues <- 
  list(
    name="emilyluckey", 
    email="emily007@gmail.com",
    time=ymd_hms("2020-03-26T08:18:40Z")
  )

commit <- list(
  author=authorValues,
  commmitter=committerValues,
  message="update"
)

print(commit)
```

```{r}
library(jsonlite) # ???֦P?ǳo???|??Error?A?ٰO?o?p???ư??ܡH
toJSON(commit)
```
```{r}
# 108-1 
course1_1081 <- 
  list(
    name="?????g?پ?",
    teacher="Alice",
    grade=85
  )
course2_1081 <-
  list(
    name="?`???g?پ?",
    teacher="Mark",
    grade=78
  )
`108-1?׽ҰO??` <- 
  list(
    course1_1081,
    course2_1081
  )

# 108-2
course1_1082 <- 
  list(
    name="?@?~???s",
    teacher="Jason",
    grade=90
  )
`108-2?׽ҰO??` <- 
  list(
    course1_1082
  )

# ???X???Ǵ?
`?C?Ǵ��׽ҰO??` <- list(
  `108-1`=`108-1?׽ҰO??`,
  `108-2`=`108-2?׽ҰO??`
)

# ?????O??
`?p?????׽ҰO??` <- 
  list(
    name="?p??",
    semesters=`?C?Ǵ��׽ҰO??`
  )

```

```{r}
library(jsonlite)
fromJSON("https://opendata.cwb.gov.tw/fileapi/v1/opendataapi/F-C0032-001?Authorization=rdec-key-123-45678-011121314&format=JSON") ->
  weather_next6hours
```


#4/12
##?s??????
```{r}
numVector <- c(2,3,6,-1,4,2,6)
select1 <- numVector[c(1,4)]; select1
select2 <- select1[[1]]; select2

# ?۷???
numVector[c(1,4)][[1]]

select1 <- numVector[c(T,T,F,T,F,F,T)]; select1
select2 <- select1[c(1,4)]; select2

# ?۷???
numVector[c(T,T,F,T,F,F,T)][c(1,4)]
```

#4/17

```{r}
a <- c("1","b","TRUE")
a
a[[2]] <- "c" # ???��s?b: ?��?
a[[4]] <- "7" # ???��??s?b?G ?W?[
a[c(5,6)] <- c("J", "K")
a
```

```{r}
print(a)
a[-c(1,3)]
a[c(-2)]

print(a)
a[-c(1,3)] -> a # ?n?^?s?~???u???R??
```
#4/30
```{r}
source("https://www.dropbox.com/s/qsrw069n94k61lj/transcript100to103_list.R?dl=1")
```

```{r}
# 只要成績大於85的
pick_above85 <-
  transcript100to103$`成績` > 85
```

```{r}
# 各學屆2年級人數
table(transcript100to103$學屆)
# 各學屆2年級成績大於85人數
table(transcript100to103$學屆[pick_above85])
```
```{r}
example <- list(
  name=c("小明","小花","小新","美美"),
  height=c(175,166,170,160),
  weight=c(77,NA,60,43),
  birthday=lubridate::ymd(c("1998-03-11","1999-12-22","1995-08-22","2001-10-10")),
  hobby=c("美食 旅遊","旅遊 時尚","3C 美食","音樂 旅遊"),
  residence=c("Taipei","New Taipei","Taichung","Kaohsiung"),
  allowance=factor(c("0-1000","1001-2000","2000+","1001-2000")),
  bloodType=c("A","B","B","O")
)
```
```{r}
str(example[c("name","height")])

pick_above170 <- example$height >= 170
example$name[pick_above170]
```

#5/08




