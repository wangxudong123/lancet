# Datetime
Package datetime supports date and time format and compare.

<div STYLE="page-break-after: always;"></div>

## Source:

- [https://github.com/duke-git/lancet/blob/main/datetime/datetime.go](https://github.com/duke-git/lancet/blob/main/datetime/datetime.go)

<div STYLE="page-break-after: always;"></div>

## Usage:
```go
import (
    "github.com/duke-git/lancet/v2/datetime"
)
```

<div STYLE="page-break-after: always;"></div>

## Index
- [AddDay](#AddDay)
- [AddHour](#AddHour)
- [AddMinute](#AddMinute)
- [BeginOfMinute](#BeginOfMinute)
- [BeginOfHour](#BeginOfHour)
- [BeginOfDay](#BeginOfDay)
- [BeginOfWeek](#BeginOfWeek)
- [BeginOfMonth](#BeginOfMonth)
- [BeginOfYear](#BeginOfYear)

- [EndOfMinute](#EndOfMinute)
- [EndOfHour](#EndOfHour)
- [EndOfDay](#EndOfDay)
- [EndOfWeek](#EndOfWeek)
- [EndOfMonth](#EndOfMonth)
- [EndOfYear](#EndOfYear)
- [GetNowDate](#GetNowDate)
- [GetNowTime](#GetNowTime)
- [GetNowDateTime](#GetNowDateTime)
- [GetZeroHourTimestamp](#GetZeroHourTimestamp)
- [GetNightTimestamp](#GetNightTimestamp)
- [FormatTimeToStr](#FormatTimeToStr)

- [FormatStrToTime](#FormatStrToTime)

<div STYLE="page-break-after: always;"></div>

## Documentation

## Note:
1. 'format' string param in func FormatTimeToStr and FormatStrToTime function should be one of flows:
- yyyy-mm-dd hh:mm:ss
- yyyy-mm-dd hh:mm
- yyyy-mm-dd hh
- yyyy-mm-dd
- yyyy-mm
- mm-dd
- dd-mm-yy hh:mm:ss
- yyyy/mm/dd hh:mm:ss
- yyyy/mm/dd hh:mm
- yyyy-mm-dd hh
- yyyy/mm/dd
- yyyy/mm
- mm/dd
- dd/mm/yy hh:mm:ss
- yyyy
- mm
- hh:mm:ss
- mm:ss


### <span id="AddDay">AddDay</span>
<p>Add or sub days to time.</p>

<b>Signature:</b>

```go
func AddDay(t time.Time, day int64) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    now := time.Now()
    after2Days := datetime.AddDay(now, 2)
    before2Days := datetime.AddDay(now, -2)

    fmt.Println(after2Days, before2Days)
}
```


### <span id="AddHour">AddHour</span>
<p>Add or sub hours to time.</p>

<b>Signature:</b>

```go
func AddHour(t time.Time, hour int64) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    now := time.Now()
    after2Hours := datetime.AddHour(now, 2)
    before2Hours := datetime.AddHour(now, -2)

    fmt.Println(after2Hours, after2Hours)
}
```

### <span id="AddMinute">AddMinute</span>
<p>Add or sub minutes to time.</p>

<b>Signature:</b>

```go
func AddMinute(t time.Time, minute int64) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    now := time.Now()
    after2Minute := datetime.AddMinute(now, 2)
    before2Minute := datetime.AddMinute(now, -2)

    fmt.Println(after2Minute, before2Minute)
}
```

### <span id="BeginOfMinute">BeginOfMinute</span>
<p>Return beginning minute time of day.</p>

<b>Signature:</b>

```go
func BeginOfMinute(t time.Time) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    td := time.Date(2022, 2, 15, 15, 48, 40, 112, time.Local)
    bm := datetime.BeginOfMinute(td)
    fmt.Println(bm) //2022-02-15 15:48:00 +0800 CST
}
```

### <span id="BeginOfHour">BeginOfHour</span>
<p>Return zero time of day.</p>

<b>Signature:</b>

```go
func BeginOfHour(t time.Time) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    td := time.Date(2022, 2, 15, 15, 48, 40, 112, time.Local)
    bm := datetime.BeginOfHour(td)
    fmt.Println(bm) //2022-02-15 15:00:00 +0800 CST
}
```

### <span id="BeginOfDay">BeginOfDay</span>
<p>Return begin time of day.</p>

<b>Signature:</b>

```go
func BeginOfDay(t time.Time) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    td := time.Date(2022, 2, 15, 15, 48, 40, 112, time.Local)
    bm := datetime.BeginOfDay(td)
    fmt.Println(bm) //2022-02-15 00:00:00 +0800 CST
}
```



### <span id="BeginOfWeek">BeginOfWeek</span>
<p>Return beginning time of week, week begin from Sunday.</p>

<b>Signature:</b>

```go
func BeginOfWeek(t time.Time) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    td := time.Date(2022, 2, 15, 15, 48, 40, 112, time.Local)
    bm := datetime.BeginOfWeek(td)
    fmt.Println(bm) //2022-02-13 00:00:00 +0800 CST
}
```



### <span id="BeginOfMonth">BeginOfMonth</span>
<p>Return beginning time of month</p>

<b>Signature:</b>

```go
func BeginOfMonth(t time.Time) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    td := time.Date(2022, 2, 15, 15, 48, 40, 112, time.Local)
    bm := datetime.BeginOfMonth(td)
    fmt.Println(bm) //2022-02-01 00:00:00 +0800 CST
}
```


### <span id="BeginOfYear">BeginOfYear</span>
<p>Return beginning time of year.</p>

<b>Signature:</b>

```go
func BeginOfYear(t time.Time) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    td := time.Date(2022, 2, 15, 15, 48, 40, 112, time.Local)
    bm := datetime.BeginOfYear(td)
    fmt.Println(bm) //2022-01-01 00:00:00 +0800 CST
}
```



### <span id="EndOfMinute">EndOfMinute</span>
<p>Return end time minute of day.</p>

<b>Signature:</b>

```go
func EndOfMinute(t time.Time) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    td := time.Date(2022, 2, 15, 15, 48, 40, 112, time.Local)
    bm := datetime.EndOfMinute(td)
    fmt.Println(bm) //2022-02-15 15:48:59.999999999 +0800 CST
}
```

### <span id="EndOfHour">EndOfHour</span>
<p>Return end time hour of day.</p>

<b>Signature:</b>

```go
func EndOfHour(t time.Time) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    td := time.Date(2022, 2, 15, 15, 48, 40, 112, time.Local)
    bm := datetime.EndOfHour(td)
    fmt.Println(bm) //2022-02-15 15:59:59.999999999 +0800 CST
}
```

### <span id="EndOfDay">EndOfDay</span>
<p>Return end time hour of day.</p>

<b>Signature:</b>

```go
func EndOfDay(t time.Time) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    td := time.Date(2022, 2, 15, 15, 48, 40, 112, time.Local)
    bm := datetime.EndOfDay(td)
    fmt.Println(bm) //2022-02-15 23:59:59.999999999 +0800 CST
}
```



### <span id="EndOfWeek">EndOfWeek</span>
<p>Return end time of week, week end with Saturday.</p>

<b>Signature:</b>

```go
func EndOfWeek(t time.Time) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    td := time.Date(2022, 2, 15, 15, 48, 40, 112, time.Local)
    bm := datetime.EndOfWeek(td)
    fmt.Println(bm) //2022-02-19 23:59:59.999999999 +0800 CST
}
```



### <span id="EndOfMonth">EndOfMonth</span>
<p>Return end time of month</p>

<b>Signature:</b>

```go
func EndOfMonth(t time.Time) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    td := time.Date(2022, 2, 15, 15, 48, 40, 112, time.Local)
    bm := datetime.EndOfMonth(td)
    fmt.Println(bm) //2022-02-28 23:59:59.999999999 +0800 CST
}
```


### <span id="EndOfYear">EndOfYear</span>
<p>Return beginning time of year.</p>

<b>Signature:</b>

```go
func EndOfYear(t time.Time) time.Time
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    td := time.Date(2022, 2, 15, 15, 48, 40, 112, time.Local)
    bm := datetime.EndOfYear(td)
    fmt.Println(bm) //2022-12-31 23:59:59.999999999 +0800 CST
}
```


### <span id="GetNowDate">GetNowDate</span>
<p>Get current date string, format is yyyy-mm-dd.</p>

<b>Signature:</b>

```go
func GetNowDate() string
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    now := time.Now()
    currentDate := datetime.GetNowDate()
    fmt.Println(currentDate) // 2022-01-28
}
```


### <span id="GetNowTime">GetNowTime</span>
<p>Get current time string, format is hh:mm:ss.</p>

<b>Signature:</b>

```go
func GetNowTime() string
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    now := time.Now()
    currentTime := datetime.GetNowTime()
    fmt.Println(currentDate) // 15:57:33
}
```


### <span id="GetNowDateTime">GetNowDateTime</span>
<p>Get current date time string, format is yyyy-mm-dd hh:mm:ss.</p>

<b>Signature:</b>

```go
func GetNowDateTime() string
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    now := time.Now()
    current := datetime.GetNowDateTime()
    fmt.Println(current) // 2022-01-28 15:59:33
}
```


### <span id="GetZeroHourTimestamp">GetZeroHourTimestamp</span>
<p>Return timestamp of zero hour (timestamp of 00:00).</p>

<b>Signature:</b>

```go
func GetZeroHourTimestamp() int64
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    now := time.Now()
    zeroTime := datetime.GetZeroHourTimestamp()
    fmt.Println(zeroTime) // 1643299200
}
```


### <span id="GetNightTimestamp">GetNightTimestamp</span>
<p>Return timestamp of zero hour (timestamp of 23:59).</p>

<b>Signature:</b>

```go
func GetNightTimestamp() int64
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    now := time.Now()
    nightTime := datetime.GetNightTimestamp()
    fmt.Println(nightTime) // 1643385599
}
```

### <span id="FormatTimeToStr">FormatTimeToStr</span>
<p>Format time to string, `format` param specification see note 1.</p>

<b>Signature:</b>

```go
func FormatTimeToStr(t time.Time, format string) string
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "time"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    now := time.Now()
    timeStr := datetime.FormatTimeToStr(now, "yyyy/mm/dd hh:mm:ss")
    fmt.Println(timeStr) //2022/01/28 16:07:44
}
```


### <span id="FormatStrToTime">FormatStrToTime</span>
<p>Format string to time, `format` param specification see note 1.</p>

<b>Signature:</b>

```go
func FormatStrToTime(str, format string) (time.Time, error)
```
<b>Example:</b>

```go
package main

import (
    "fmt"
    "github.com/duke-git/lancet/v2/datetime"
)

func main() {
    time := datetime.FormatStrToTime("2006-01-02 15:04:05", "yyyy/mm/dd hh:mm:ss")
    fmt.Println(time)
}
```



