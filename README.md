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


# list含兩個lists, 子層list又各含兩個vectors
```{r}
`小明108學年課表C` <- list(
  `108學年第1學期`=list(
    c("108-1"), # 可只寫 "108-1"
    c("高級會計學","高等統計學")
       ),
  `108學年第2學期`=list(
    c("108-2"),
    c("食在拉丁美洲")
  )
)
print(`小明108學年課表C`)
```


```{r}
# list含兩個lists, 子層list又各含兩個vectors
"小明108學年課表C" <- list(
  `108學年第1學期`=list(
    "108-1", # 可只寫 "108-1"
    'course'=c("高級會計學","高等統計學")
       ),
  `108學年第2學期`=list(
    c("108-2"),
    c("食在拉丁美洲")
  )
)
print(`小明108學年課表C`)
```

```{r}
commit <- list(
  author = c("Martin老師", "mtlin@gm.ntpu.edu.tw", "2020-03-25T07:17:40Z"),
  committer = c("emilyluckey", "emily007@gmail.com", "2020-03-26T08:18:40Z"),
  message = c("update")
)
print(commit)
```

```{r}
library(lubridate)
authorValues <- 
  list(
    name="Martin老師",  
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
library(jsonlite) # 不少同學這行會有Error，還記得如何排除嗎？
toJSON(commit)
```
```{r}
# 108-1 
course1_1081 <- 
  list(
    name="個體經濟學",
    teacher="Alice",
    grade=85
  )
course2_1081 <-
  list(
    name="總體經濟學",
    teacher="Mark",
    grade=78
  )
`108-1修課記錄` <- 
  list(
    course1_1081,
    course2_1081
  )

# 108-2
course1_1082 <- 
  list(
    name="作業研究",
    teacher="Jason",
    grade=90
  )
`108-2修課記錄` <- 
  list(
    course1_1082
  )

# 整合兩學期
`每學期修課記錄` <- list(
  `108-1`=`108-1修課記錄`,
  `108-2`=`108-2修課記錄`
)

# 完成記錄
`小明的修課記錄` <- 
  list(
    name="小明",
    semesters=`每學期修課記錄`
  )

```

```{r}
library(jsonlite)
fromJSON("https://opendata.cwb.gov.tw/fileapi/v1/opendataapi/F-C0032-001?Authorization=rdec-key-123-45678-011121314&format=JSON") ->
  weather_next6hours
```


#4/12
##連鎖選取
```{r}
numVector <- c(2,3,6,-1,4,2,6)
select1 <- numVector[c(1,4)]; select1
select2 <- select1[[1]]; select2

# 相當於
numVector[c(1,4)][[1]]

select1 <- numVector[c(T,T,F,T,F,F,T)]; select1
select2 <- select1[c(1,4)]; select2

# 相當於
numVector[c(T,T,F,T,F,F,T)][c(1,4)]
```









