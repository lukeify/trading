<%* 
ticker = await tp.system.prompt("Ticker");
dir = await tp.system.suggester(["Long", "Short"], ["Long", "Short"]);
count = await tp.system.prompt("Count");
%>

### <% ticker %> <% dir %> (#<% count %>)

Entries:
- Entry

Exits:
- Exit

P&L (%):

![Trade Chart](../images/trades/<% tp.file.title.split("_")[0] %>/<% ticker %>_<% count %>.png)
