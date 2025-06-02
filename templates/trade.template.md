<%*
ticker = await tp.system.prompt("Ticker");
dir = await tp.system.suggester(["Long", "Short"], ["Long", "Short"]);
count = await tp.system.prompt("Count");
trade_time = await tp.system.prompt("Trade Time");
trade_type = await tp.system.prompt("Trade Type");
%>

### <% ticker %> <% dir %> (#<% count %>) — <% trade_time %>

Trade type: <% trade_type %>

Provide an explanation of the trade, chronologically, while also answering questions like:

- How did I find the opportunity to trade this stock?
- What was my rationale for entry?
- What was the quality of my entry from a risk:reward perspective? Did it go according to plan?
- How much did I risk? How did you manage your position sizing?
- How was my exit execution?
- Did I take profit too early?

#### Environmental

* What was my physical and emotional wellbeing when I took the trade?

#### #### What went right about this trade?

- How accurate was my technical analysis?
- What contributed to this being a good trade?

#### What was wrong about this trade?

- Is there anything I could improve next time?
- Did I lack discipline? Was I scared?
