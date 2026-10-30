# Hiro playbooks

Each playbook is the message the creator would send. Run the steps as written. "Soul first" means: call `get_show_soul` first, work from the Show Soul and the live numbers, and write in the voice stored in the soul. Every playbook that does work for the creator ends with `log_agent_run` so the next session knows where to pick up. Replace SHOW_ID with the show's id from `list_shows`.

## Set up

### Set up my show soul
1. Call `get_show_soul` and read the snapshot and episodes.
2. Ask one question at a time: who the show is for, the problem it solves, the promise, the offer after the show (name, price, link), the creator's story, and the current goal with a target and date. Save with `update_show_identity`.
3. Finish with `log_agent_run`.

### Learn my voice from my episodes
1. Call `get_show_soul`. Pick the 3 most downloaded episodes with a transcript.
2. Read them with `get_episode_transcript`. Choose 2 or 3 short excerpts that sound most like the creator, name the tone, list words they use and words to avoid.
3. Show them, adjust, then save with `update_show_voice`. Finish with `log_agent_run`.

### Find the best moment in each episode
1. Call `get_show_soul`. For each published episode with a transcript, read it with `get_episode_transcript`.
2. Pick the single strongest 20 to 60 second moment: a clear idea, a story turn or a line worth quoting. Note start, end, the quote and why it works.
3. Save each with `add_show_moment`. Finish with `log_agent_run`.

## Create content

### Write this week's email to my listeners about my newest episode
Soul first. Use the newest published episode and its best moment if one is saved. One email, under 200 words, one link to listen, one clear next step. Give a subject line and two alternatives. The creator sends it from Hiro's broadcasts (https://app.hiro.fm/products/SHOW_ID/campaigns). Finish with `log_agent_run`.

### Write a 5-email welcome series for new listeners
Soul first. Email 1 welcomes and points to the first episode. Emails 2 to 4 each use one best moment. Email 5 introduces the offer after the show. Under 180 words each, subject lines included. The creator loads them into a Hiro automation (https://app.hiro.fm/products/SHOW_ID/automations). Finish with `log_agent_run`.

### Turn an episode into 10 Instagram captions and a LinkedIn post
Soul first. Ask which episode if not given. Read it with `get_episode_transcript`. Each caption stands alone, uses one idea or quote, ends with a reason to listen. The LinkedIn post is 150 to 250 words, no hashtags. Save any quotes you used with `add_show_moment`. Finish with `log_agent_run`.

### Write the clip captions for the best moment in each episode
Soul first. For every saved best moment, write a caption for a 30 to 60 second clip: a hook line, one sentence of context, and where to listen. Group by episode. If an episode has no saved moment, say so. Finish with `log_agent_run`.

### Plan my next 6 episodes based on what listeners download most
Soul first. Rank episodes by downloads and completion from the snapshot. Name the topics and formats that win. Propose 6 episodes: title, one-line promise, 3 talking points, and the best moment style to aim for. Regular episodes the creator records themselves. If they need an expiring mini-course that sells their offer, send them to Producer (https://app.hiro.fm/producer) instead of planning it here. Finish with `log_agent_run`.

### Write me 5 better titles and descriptions for my show
Soul first. Each option names the listener and the promise from the identity. Titles under 60 characters, descriptions under 300. Label them option 1 to 5 so the creator can pick one. Finish with `log_agent_run`.

### Make this month's content plan
Soul first. Work from the current goal. Week by week: episode to release, one email, three social posts, and which best moment each uses. Mark the Hiro tool for each step: broadcasts, automations, Publisher for a newsletter (https://app.hiro.fm/publisher), Promoter for finding listeners (https://app.hiro.fm/promoter?show=SHOW_ID). Finish with `log_agent_run`.

### Review an episode and tell me what to improve
Soul first. Ask which episode if not given. Read it with `get_episode_transcript` and use `get_episode_playthrough` for drop-off if that data exists. Cover: the opening, parts that drag, where it should end, the call to action, filler words, whether the title matches the content, 3 clip-worthy sections (save them with `add_show_moment`), and where listeners drop off. Short, specific, with timestamps. Finish with `log_agent_run`.

## Reuse content

### Turn each episode into a carousel or quote graphic for Instagram and Pinterest
Soul first. For each published episode: pick a carousel (5 to 7 slides of text) or a single quote graphic, write the slide or quote text, an alt text and a caption. Use saved best moments first. Finish with `log_agent_run`.

## Hiro tools

These route the creator to the right Hiro tool. Do not do the work yourself.

### I want more leads or booked calls
Call `get_show_soul`, confirm the offer in the identity, then send the creator to Producer: https://app.hiro.fm/producer. It reads their offer page, PDF or free text and builds an expiring mini-course that sells that offer. Tell them what to paste into it from the soul (audience, problem, promise, offer).

### I want a free series or lead magnet
Call `get_show_soul`, then send the creator to Producer: https://app.hiro.fm/producer. It builds the expiring free series from their offer or notes. Tell them what to paste into it from the soul.

### Turn my book, PDF or doc into episodes
Send the creator to Page Turner: https://app.hiro.fm/page-turner. Tell them in three lines what it does and what to upload.

### Make a newsletter from my episodes
Send the creator to Publisher: https://app.hiro.fm/publisher. Tell them in three lines what it does and which episodes to start with, from the snapshot in `get_show_soul`.

### Find listeners for my show
Call `get_show_soul`, then send the creator to Promoter: https://app.hiro.fm/promoter?show=SHOW_ID. Tell them in three lines what it does and what from the identity to use in it.

### Make new cover art
Call `get_show_soul`, then send the creator to the cover art maker on the Grow page: https://app.hiro.fm/grow?show=SHOW_ID. Suggest a short title treatment and mood from the identity.

### Nudge listeners who haven't played in 30 days
Call `get_show_soul`, then send the creator to the show's automations in Hiro: https://app.hiro.fm/products/SHOW_ID/automations. Draft the one nudge message in their voice, under 120 words, pointing to the best moment of the newest episode. The automation sends it.

## Find listeners

### Write a pitch to get me on a podcast as a guest
Soul first. Under 150 words: who the creator helps, one specific result or story from a best moment, three episode ideas for the host's audience, and one line on why those listeners would care. Give a subject line. Finish with `log_agent_run`.

### Check what ChatGPT and Perplexity recommend for my topic, and where I show up
Call `get_show_soul` for the niche and topic. Search the web for the questions the listener would ask and note what ChatGPT, Perplexity and Google AI answers recommend. Report whether the show or the creator's name appears, who does, and three concrete things to change on the sales page or episode titles. Record the baseline with `log_result` (type other). Finish with `log_agent_run`.

## Sell

### Make me a plan to hit a listener number by a date
Ask for the target (for example 500 listeners) and the date if not given. Soul first. Save the goal with `update_show_identity`. From the last 30 and 90 days work out the weekly gap. Pick the sources to use (Promoter for listeners, partners, social, email), set a weekly number per source, and create a tracked link for each with `add_tracked_link`. Give the week one actions. Finish with `log_agent_run`.

### What should my next paid offer be, based on my episodes?
Soul first. Use the top episodes by downloads and completion, the saved moments and the current offer. Propose 3 offers: name, who it is for, the result, price range, and which episodes prove the demand. Recommend one. If the goal is leads or calls, say Producer (https://app.hiro.fm/producer) builds the mini-course that sells it. Finish with `log_agent_run`.

## Improve

### What's the one thing holding my show back right now?
Soul first. Compare visits, opt-ins, completion and sales against the current goal. Name the single bottleneck and one action for it. Skip anything in dismissedSuggestions. If the creator agrees to a change, record it with `log_change` with the number it should move and a re-check date. Finish with `log_agent_run`.

### Which episode loses the most people?
Call `get_show_soul`. Compare per-episode downloads, plays and completions for the last 90 days; use `get_episode_playthrough` on the suspects. Name the episode, where listeners leave, and the likely reason from the transcript. Completion covers Hiro app and web listeners only; say so. Finish with `log_agent_run`.

### How does my sales page compare to the top shows in my niche?
Soul first. Read the sales page copy and setup from the snapshot. Search the web for 3 leading shows or courses in the same niche and compare: headline promise, proof, offer clarity, call to action, FAQ, guarantee. Give a rewrite of the headline and first paragraph. Finish with `log_agent_run`.

### Which free sample episode turns into the most sales?
Call `get_show_soul`. Use the sample episodes, their downloads and the sampleToSales numbers in the snapshot, and `get_sales` for the period. Rank the samples and say which to feature on the sales page. Finish with `log_agent_run`.

### Change my show description to option 2
Ask which option if not given. Show the exact old and new text. The creator makes the change in Hiro (https://app.hiro.fm/products/SHOW_ID). Once they confirm, record it with `log_change`: before, after, the metric (sales page conversion), the baseline and a re-check date 14 days out. Finish with `log_agent_run`.

### How did last week's changes do?
Call `get_show_soul` with the full history. For each change whose re-check date has passed, read the current number, decide better, worse or same, and call `update_change_outcome`. Five lines: what moved, what did not, one thing to do this week. Finish with `log_agent_run`.

## Routine

### Send me a report on my show every Monday
If you can schedule recurring tasks, schedule this every Monday morning; otherwise run it now and say how to repeat it. The report: call `get_show_soul`, then ten lines: new listeners, visits, opt-ins, sales and completion for the last 7 days against the 7 before, tracked link results, open changes due for re-check, and one action. Finish with `log_agent_run`.

### Review this month's numbers against last month, by source
Call `get_show_soul`. Compare the last 30 days with the 30 before for visits, opt-ins, sales and completion. For each tracked link ask the creator for the latest clicks, opt-ins and sales and save them with `record_link_results`, then rank the sources. Say what to do more of and what to stop. Finish with `log_agent_run`.
