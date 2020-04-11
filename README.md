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


# list�t���lists, �l�hlist�S�U�t���vectors
```{r}
`�p��108�Ǧ~�Ҫ�C` <- list(
  `108�Ǧ~��1�Ǵ�`=list(
    c("108-1"), # �i�u�g "108-1"
    c("���ŷ|�p��","�����έp��")
       ),
  `108�Ǧ~��2�Ǵ�`=list(
    c("108-2"),
    c("���b�ԤB���w")
  )
)
print(`�p��108�Ǧ~�Ҫ�C`)
```


```{r}
# list�t���lists, �l�hlist�S�U�t���vectors
"�p��108�Ǧ~�Ҫ�C" <- list(
  `108�Ǧ~��1�Ǵ�`=list(
    "108-1", # �i�u�g "108-1"
    'course'=c("���ŷ|�p��","�����έp��")
       ),
  `108�Ǧ~��2�Ǵ�`=list(
    c("108-2"),
    c("���b�ԤB���w")
  )
)
print(`�p��108�Ǧ~�Ҫ�C`)
```

```{r}
commit <- list(
  author = c("Martin�Ѯv", "mtlin@gm.ntpu.edu.tw", "2020-03-25T07:17:40Z"),
  committer = c("emilyluckey", "emily007@gmail.com", "2020-03-26T08:18:40Z"),
  message = c("update")
)
print(commit)
```

```{r}
library(lubridate)
authorValues <- 
  list(
    name="Martin�Ѯv",  
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
library(jsonlite) # ���֦P�ǳo��|��Error�A�ٰO�o�p��ư��ܡH
toJSON(commit)
```
```{r}
# 108-1 
course1_1081 <- 
  list(
    name="����g�پ�",
    teacher="Alice",
    grade=85
  )
course2_1081 <-
  list(
    name="�`��g�پ�",
    teacher="Mark",
    grade=78
  )
`108-1�׽ҰO��` <- 
  list(
    course1_1081,
    course2_1081
  )

# 108-2
course1_1082 <- 
  list(
    name="�@�~��s",
    teacher="Jason",
    grade=90
  )
`108-2�׽ҰO��` <- 
  list(
    course1_1082
  )

# ��X��Ǵ�
`�C�Ǵ��׽ҰO��` <- list(
  `108-1`=`108-1�׽ҰO��`,
  `108-2`=`108-2�׽ҰO��`
)

# �����O��
`�p�����׽ҰO��` <- 
  list(
    name="�p��",
    semesters=`�C�Ǵ��׽ҰO��`
  )

```

```{r}
library(jsonlite)
fromJSON("https://opendata.cwb.gov.tw/fileapi/v1/opendataapi/F-C0032-001?Authorization=rdec-key-123-45678-011121314&format=JSON") ->
  weather_next6hours
```


#4/12
##�s����
```{r}
numVector <- c(2,3,6,-1,4,2,6)
select1 <- numVector[c(1,4)]; select1
select2 <- select1[[1]]; select2

# �۷��
numVector[c(1,4)][[1]]

select1 <- numVector[c(T,T,F,T,F,F,T)]; select1
select2 <- select1[c(1,4)]; select2

# �۷��
numVector[c(T,T,F,T,F,F,T)][c(1,4)]
```









