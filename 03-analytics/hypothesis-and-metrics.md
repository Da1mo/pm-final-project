# Hypothesis & Success Metrics (Module 3)

## Pre-work · Hypothesis check
- **Role , who you are solving for (from M2):** The Overwhelmed Regular. A long-time, heavily engaged subscriber who opens StreamLine most evenings out of habit, but increasingly leaves without watching anything.
- **Goal , what this user is ultimately trying to achieve:** To find something good to watch tonight quickly and confidently, without the decision feeling like work.
- **Friction / moment of misery , the specific pain blocking their goal:** After twenty minutes of scrolling through 15,000 titles, the user still has nothing they want to watch, so they close the app and fall back on something familiar outside it, like a DVD or the same few comfort shows.
- **Current workaround , the external tool or manual process they rely on (M2):** They leave the app for a smaller, familiar set of options. Either they pick from their own DVD shelf, or they stay in the app but skip discovery and re-watch the same four comfort shows.
- **Problem Hook , your one-sentence framing of the business crisis (M1):** Our most loyal subscribers are scrolling through 15,000 titles, finding nothing worth their evening, and leaving for DVDs, re-watches or curated competitors, which turns StreamLine’s biggest asset into the reason they disengage and cancel.
- **Value Proposition , the outcome your initiative promised to deliver (M1):** Spotlight turns an overwhelming 15,000-title library into a few trusted, human-picked choices each night, so loyal subscribers spend their evening watching rather than scrolling. Launching now with editorial collections from our existing catalogue lets us win back engagement before more viewers leave for curated competitors.

## Read your data snapshots
- **Does the funnel data confirm your M2 friction point, or does it tell a different story? Note where the numbers align with the qualitative pain you found and where they diverge.:** The funnel partly confirms the M2 friction point, but it also shows a second problem the interviews played down. Users struggle to choose, as the research found, and many who do choose don’t stay long.
Where the numbers match the research
Browsing without watching. 71% of visitors browse titles, but only 29% start playing, so about 59% of people who browse never press play. That is Priya’s moment of misery at scale: twenty minutes of scrolling and nothing watched (UXR-01).
Discovery failing. Searches that end in playback fell from 41% to 34% in six months. That matches the exact-title-only search problem (BUG-1080) and Lucia’s “slow quiet French drama” query (UXR-07).
Engagement declining. Average session length fell 23% (31 → 24 min). That fits users who give up quickly or retreat to short comfort re-watches (UXR-03).
Where they tell a different story
The steepest drop comes after play, not before. Of the 29% who start playing, only 11% reach 30 minutes, so about 62% of plays end early. The M2 friction is about failing to choose. This suggests that even users who do choose often abandon what they picked. Two causes are possible: curation that doesn’t fit what they wanted, and the stability bugs, such as buffering drops (BUG-1042) and lost resume positions (BUG-1061). Spotlight addresses the first cause but not the second.
We’re losing reach, not just depth. Mobile daily active users are down 21%, about 400,000 fewer a day. The qualitative research doesn’t explain the scale of this loss, and the snapshot’s claim that “the top of the funnel is holding” hides it.
The data may not cover the persona’s context. The data covers mobile only, but the persona’s evening viewing, and both sync bugs, involve the TV. The funnel may understate the friction for this persona, or simply measure a different group of users.


The data supports choice overload as a real, measurable problem, so Spotlight is still justified. But on its own Spotlight would only fix the choosing problem. To win back time spent watching, the stability and sync bugs need to be fixed. Still before counting this as proof, this data only has evidence for mobile. So I'd need TV funnel data and six-month comparison for each funnel stage.
- **Do the retention patterns align with the workaround your M2 persona used to find content? Note what the Mo. 0→1 drop suggests about the onboarding experience your persona described as frustrating.:** Partly supports the M2 workaround. The research doesn't give any data on onboarding. M2 persona is a long time subscriber, so anything about the first month is an inference.
The M2 workaround works by shrinking the choice. That worked. 
The month 0 -> 1 suggests new subscribers face the overload with no fallback, the recommendations have nothing to work with yet and spotlight only fixes part of the drop.
- **Does the LTV gap and the content mix (61% trending for Wanderers) confirm the moment of misery your persona described? Note which segment your persona is in and whether the data confirms their pain.:** The data confirms the mechanism behind the moment of misery, but my M2 persona sits in the segment with the least at stake.
Which segment the persona is in: My persona, a long-time subscriber who opens the app most evenings, behaves like a Power User (4.8 sessions a week). Priya, a heavy viewer for 14 years, fits that. But Aisha describes herself as casual, so the persona actually combines Power Users and Casual Browsers.
The moment of misery is real, but it costs the business most among Wanderers (41% of the base, the biggest churn improvement), not among Power Users. I’d re-target the persona: same twenty-minute scroll, but a Wanderer who cancels instead of reaching for a DVD.
- **Does the low adoption confirm your persona is burdened by tools they don’t use? Note whether the low scheduling adoption (42%) for coordinators matches your M2 moment of misery.:** _(not filled in)_
- **Does the workflow data match the manual process or hack you documented in M2? Note whether the specific drop-offs or time gaps explain why your persona avoids the digital tool.:** _(not filled in)_
- **Look at the CSAT heatmap. Which specific cell most directly maps to your persona’s friction? Note how the NPS trend justifies the urgency of your M1 Problem Hook.:** _(not filled in)_

## Step 3 · Craft your hypothesis
- **Qualitative evidence (from M2) , quote the specific friction / moment of misery for your persona:** “There’s 15,000 titles but nothing I actually want. I ended up going back to a DVD.” (Priya, UXR-01).
She scrolled for twenty minutes, closed the app without watching anything, and left the product to find something to watch.
- **Quantitative evidence (from M3) , name the metric or data point that confirms the pain; cite the number:** Main data point: 71% of homepage visitors browse titles, but only 29% start playing, so about 59% of people who browse never press play (Snapshot 1, conversion funnel). That’s Priya’s moment of misery measured at scale: scrolling, then leaving without watching anything.

Engagement is getting shallower. Sessions reaching 30+ minutes fell from 19% to 11%, and average session length fell from 31 to 24 minutes over six months (Snapshot 1).
Shrinking the choice keeps people. Spotlight cohorts retain 74–79% at Month 1, against 63–68% for Full Library cohorts, and 52% against 34–39% at Month 3 (Snapshot 2).
The pain costs the most among Wanderers. They’re 41% of the base and rely on Trending for 61% of what they watch. Exposure to Spotlight cuts their churn by 22 points, the largest drop of any segment (Snapshot 3).
- **Persona , role, goal, and the friction you confirmed in the reconciliation steps:** Persona: The Wanderer
Role: An infrequent subscriber (about one session a week) who relies on the generic Trending rows for 61% of what they watch, and makes up the largest share of the base (41%).
Goal: To find something good to watch quickly and confidently, without having to search through a huge catalogue to get there.
Confirmed friction: They scroll through 15,000 titles, find nothing that feels personal, and leave without watching. They haven’t built Priya’s fallbacks, a DVD shelf or comfort shows, so for them the moment of misery ends in cancelling.
How the reconciliation steps confirmed it
The pain (qualitative): Priya’s “15,000 titles but nothing I actually want” (UXR-01).
The pain at scale (Snapshot 1): about 59% of people who browse never press play.
Where it costs the most (Snapshot 2): the biggest leak is Month 0 → Month 1, before users build a viewing habit.
Who it costs the most (Snapshot 3): Wanderers’ churn falls by 22 points when they’re exposed to Spotlight, the largest improvement of any segment.
- **Problem you are solving , one sentence describing the specific friction this initiative removes:** Wanderers who face 15,000 titles with no personal route through them scroll, find nothing worth watching, and leave without pressing play. This initiative replaces that dead end with a small, trusted set of curated picks.
- **Strategic outcome , what behaviour change do you expect, and how does it map to retention / revenue / churn?:** Strategic outcome
Expected behaviour change: Wanderers stop leaving after browsing. Instead they start watching from a short set of curated picks, and they keep watching. In practice that means:
More browsers press play. Today about 59% of people who browse never start anything.
More sessions run past 30 minutes. That share has fallen from 19% to 11%.
Wanderers come back more often. Today they use the app about 1.1 times a week, and the aim is to build a regular habit.
How it maps to the business
Outcome	Evidence	Expected impact
Churn	Wanderers exposed to Spotlight churn 22 points less	Lower cancellations in the largest segment (41% of the base)
Retention	Spotlight cohorts retain about 11 points better at Month 1 and 13–18 points better by Month 3	Smaller Month 0 → Month 1 drop, which is the biggest leak
Revenue	41% of the base × $8.40 monthly LTV × 22-point churn reduction	About $76 a month protected per 100 subscribers, the highest of any segment
Summary line for the table: Wanderers move from browsing and leaving to watching curated picks every week, which cuts their churn by up to 22 points and protects the largest share of recurring revenue.
- **Primary success metric (initiative signal) , the leading indicator that tells you the gap is closing:** The Wanderer watch-through rate, meaning the share of Wanderer sessions that start a Spotlight pick and reach 30+ minutes.
Why this metric
It’s a leading indicator. It moves within days or weeks, long before churn shows up in the Month 1 retention figures.
It measures the gap directly. The friction is browsing without watching. This metric captures both halves: whether Wanderers start something, and whether they stay with it. Counting clicks or adoption, like Spotlight’s current 18% figure, would miss the second half.
It predicts the lagging outcomes. Depth of viewing is the stage that’s been declining, and it’s the behaviour that should reduce churn and protect LTV.
Baseline and target
Baseline: 11% of sessions reach 30+ minutes across the base today (Snapshot 1). Wanderers’ own figure needs pulling, and it’s likely lower.
Target: back to 19%, the level from six months ago. It’s a realistic goal because the product has already achieved it.
- **Guardrail metric (product signal) , the metric that must NOT drop; it protects your existing base:** Power User sessions per week, currently 4.8, which must not fall.
Why this is the guardrail
It protects the most valuable users. Power Users are 22% of the base, have the highest monthly LTV ($14.20) and rarely churn. Losing even a few of them costs more per head than any other segment.
They’re the users Spotlight is most likely to annoy. Moving curated picks to the top of the home screen changes a layout Power Users already navigate well, since 58% of what they watch is already curated. If Spotlight gets in their way, their sessions drop before their churn does.
The premium tier puts them at risk. If features they currently use move behind a paywall, Power Users are the ones most likely to notice and push back.
Threshold: Pause the rollout and investigate if Power User sessions fall below 4.5 a week (a drop of about 6%), or if their churn rises above its current baseline.
- **Decision window , how much time or data before you scale, pivot, or kill? minimum threshold to proceed?:** 12 weeks, run as a controlled test: Wanderers randomly split between Spotlight and a holdout group that keeps the Full Library experience.
Why 12 weeks
It gives two full monthly cohorts a Month 1 result. The biggest leak is Month 0 → Month 1, so we need at least two cohorts reaching Month 1 to see whether the effect holds.
It allows an early Month 2 or Month 3 signal. That’s where the retention gap widened in Snapshot 2 (13–18 points by Month 3).
The holdout fixes the current data’s main weakness. Today’s numbers compare cohorts and users who chose Spotlight themselves. A random split shows the real effect, separate from seasonality and from users who chose Spotlight.
The sample size is enough. Wanderers are 41% of the base, so several hundred thousand users can take part.
Weekly checks: the Wanderer watch-through rate (leading) and Power User sessions a week (guardrail).
Decision thresholds at week 12 (compared with the holdout group)
Decision	Condition
Scale	Wanderer watch-through rate is up at least 4 points, Month 1 churn is down at least 10 points, and Power User sessions stay at or above 4.5 a week
Pivot	Watch-through rises but churn doesn’t move, so people watch more but still cancel. Look at other causes, such as the bugs or pricing
Kill	No meaningful lift in either metric against the holdout, or the guardrail is breached
Minimum threshold to proceed: a 10-point Month 1 churn reduction for Wanderers against the holdout. That’s about half the 22 points observed so far, which deliberately allows for the selection bias in the current data. If the real effect falls short even of that, the initiative isn’t worth scaling.
Stop early if Power User sessions fall below 4.5 a week for two weeks in a row.
- **Draft your full hypothesis sentence , one to three sentences; quote the metric, name the persona, name the outcome:** Based on Priya’s “15,000 titles but nothing I actually want” (UXR-01) and the funnel data showing that about 59% of people who browse never press play, I believe that replacing endless scrolling with a small set of trusted, human-curated picks for Wanderers (41% of the base, mostly watching Trending, the most likely to churn) will result in more viewing that lasts and fewer first-month cancellations, as measured by a 4-point increase in the Wanderer watch-through rate (sessions that reach 30+ minutes from a Spotlight pick). I will protect Power User sessions per week (no lower than 4.5) and will make a go/no-go decision after a 12-week controlled test against a Full Library holdout group, requiring at least a 10-point reduction in Wanderer Month 1 churn to scale.
