#### Convert time using Powershell
```
[int][DateTimeOffset]::new((Get-Date "2023-04-01 13:12:00").ToUniversalTime()).ToUnixTimeSeconds()
# output: 1680325920
```

+8 to UTZ
```
(Get-Date "2023-04-01 1:00:00 +0800").ToUniversalTime().ToString("yyyy-MM-dd HH:mm:ssZ")
# output: 2023-03-31 17:00:00
```

UTC to +8 Timezone
```
(Get-Date -Date "2023-04-01 14:30:00Z").ToUniversalTime().AddHours(8).ToString("yyyy-MM-dd HH:mm:ss")
# output: 2023-04-01 22:30:00
```

epoch to UTC
```
[DateTimeOffset]::FromUnixTimeSeconds(1680325920).ToUniversalTime().ToString("yyyy-MM-dd HH:mm:ssZ")
# output: 2023-04-01 05:12:00Z
```

epoch to MYT (+8)
```
[DateTimeOffset]::FromUnixTimeSeconds(1680325920).ToUniversalTime().AddHours(8).ToString("yyyy-MM-dd HH:mm:ss")
# output: 2023-04-01 13:12:00
```
