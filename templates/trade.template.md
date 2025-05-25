<%* 
ticker = await tp.system.prompt("Ticker");
dir = await tp.system.suggester(["Long", "Short"], ["Long", "Short"]);
count = await tp.system.prompt("Count");
trade_time = await tp.system.prompt("Trade Time");
trade_type = await tp.system.prompt("Trade Type");
%>

### <% ticker %> <% dir %> (#<% count %>) — <% trade_time %>

<% trade_type %>

Description.

#### #### What was good about this trade?

* Good line item

#### What was bad about this trade?

- Bad line item

![Trade Chart](../images/trades/<% tp.file.title.split("_")[0] %>/<% ticker %>_<% count %>.png)
