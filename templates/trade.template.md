<%* 
ticker = await tp.system.prompt("Ticker");
dir = await tp.system.suggester(["Long", "Short"], ["Long", "Short"]);
count = await tp.system.prompt("Count");
%>

### <% ticker %> <% dir %> (#<% count %>)
