**🎬 Netflix Data Engine **

**Part 1: Collection**

*Explicit data (what I deliberately tell Netflix):*
- Shows I save to watch later (My List) – signals intention, not necessarily enjoyment
- Keyword searches – bonus: failed searches show Netflix what people want but can't find
- Thumbs up/down ratings – though most people rarely rate, so this data is sparse
- Clicking "Not interested" – rare but valuable negative feedback; scrolling past is ambiguous, this isn't

*Implicit data (what Netflix observes in the background):*
- Time of day / weekday vs weekend – raw timestamps aren't useful alone, but turned into features they show context (light shows in the morning, films on weekends) and even *who* is watching on a shared profile
- How long I watched – finishing vs dropping off after 5 mins
- Which trailers/previews I watched or lingered on

*Most reliable signal:* How long I watch – especially whether I finish a title or binge the next episode. Time is costly and hard to fake, so it reflects what I actually enjoy, while searches, saves and ratings show what I'm curious about or *say* I like. Costly behaviour beats cheap words.

**Part 2: Structured vs Unstructured – the thumbnail trick** Netflix uses unstructured data (images) to personalise the "packaging" of the same film. For a spy movie with a love story, I'd see a romantic scene (I watch romance), while my friend who watches action would see an explosion. *How does Netflix know which image works?* Trial and error at scale (A/B testing) – show different thumbnails to different groups and measure what gets clicked. *Where's the trick?* If a romantic thumbnail lures me into a film that's 90% action, I'll quit early. So a good thumbnail is measured by clicks + watch time, not clicks alone. High clicks with early drop-offs = clickbait, and watch-time data (my most reliable signal from Part 1) exposes it. The fix: keep thumbnails true to the film's main genre. *Combining explicit + implicit:* Netflix can check whether users who picked a genre in their profile actually finish films shown with that genre's thumbnail. If romance fans keep dropping off "romantic-looking" films, either the thumbnail misled them or their stated preference doesn't match their real taste – behaviour corrects both.

**Part 3: The Algorithm** Netflix would recommend *Better Call Saul* to User B. Both users watched Breaking Bad, so the algorithm assumes similar taste and recommends what User A watched next. This is **collaborative filtering** – "people who liked what you liked will like what they liked next." It needs no understanding of the shows, just patterns between viewers. One similar user is a hunch; thousands are evidence. *Where it breaks:* a brand-new show has no viewers yet, so it can't be recommended this way (the **cold start problem** – same for new users). Real systems blend in **content-based filtering** (genre, cast, creator). **Part 4: Ethics – the "Bubble"** I don't think it's a major ethical issue for Netflix – it's entertainment, so the stakes are low. A bubble of rom-coms is harmless; a bubble of one-sided political news would be far more serious. Same algorithm, different stakes. Still, a good fix: occasionally recommend something outside my usual taste, e.g. a trending show, to test whether my preferences expand – the **explore vs exploit** trade-off. *Counterpoint:* Netflix optimises for watch time, not my wellbeing. Autoplay and "next episode" countdowns keep me watching – so the bigger ethical issue might be bingeing, not the bubble.