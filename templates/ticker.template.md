<%* ticker = await tp.system.prompt("Ticker") %>

### <% ticker %>

Identified from: 

| Key         | Value | Classification | Source |
| ----------- | ----- | -------------- | ------ |
| Market Cap. |       |                |        |
| Float       |       |                |        |
| Avg. Volume |       |                |        |
| ATR         |       |                |        |

![<% ticker %> Chart](../images/charts/<% tp.file.title.split("_")[0] %>/<% ticker %>.png)
