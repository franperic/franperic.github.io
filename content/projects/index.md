---
title: "Projects"
showtoc: false
---

Here is an overview of the projects I have worked on:

[Law Bot](https://law-bot-frontend.web.app/) [WIP]
{{< rawhtml>}}

<figure>
    <img src="/zmittag/lawbot.png" style="height:500px;margin:auto;display:block">
</figure>
<!-- <div align="center"><i>Image generated with Midjourney</i></div> -->
<br>
{{< /rawhtml>}}

> Goal: Answer legal questions about the Swiss law (POC with the Swiss Civil Code).

- Scrape legal texts from the Swiss Civil Code.
- Embed the texts using word embeddings.
- At query time, find the most similar text to the user's question and provide the context + query to a LLM.

---

[Lunch App](https://zmittag.io)
{{< rawhtml>}}

<figure>
    <img src="/zmittag/snapshot.png" style="height:500px;margin:auto;display:block">
</figure>
<!-- <div align="center"><i>Image generated with Midjourney</i></div> -->
<br>
{{< /rawhtml>}}

> Goal: Aggregates daily lunch menus at restaurants in Baden, Switzerland.

- Scrape lunch menus at predefined restaurants.
- Store menus in a database.
- The web app fetches today's menu and displays it to the user.
