https://claude.ai/artifact/HdmmVDmJxc3AJiDeL4YfJN

# A1 · Spotlight Curated Rail Hand-picked homepage rail that bypasses the algorithm, Simplified PRD (StreamLine)

**Author:** Me · **Status:** Draft · **Target:** High-Fidelity Prototype · **Persona:** The Wanderer

## 1. The Big Picture
- **Vision:** To eliminate the twenty-minute scroll that ends with Wanderers leaving StreamLine without watching anything, by replacing 15,000 choices with a handful of trusted, human-curated picks at the top of every home screen
- **Press release:** Today, StreamLine launched Spotlight, a new way to find something great to watch in seconds. Every time subscribers open the app, Spotlight puts a small set of titles hand-picked by StreamLine's editors at the top of the home screen. The picks are refreshed every week and play with one tap.

Spotlight brings the expertise of real curators to every evening, whether that's a hidden classic, a new favourite or the perfect film for a quiet night in. It's available now on mobile, with TV coming soon.
- **Success metric:** Wanderer watch-through rate, meaning the share of Wanderer sessions that start a Spotlight pick and reach 30+ minutes
- **Guardrail:** Power User sessions per week, currently 4.8, must not fall below 4.5

## 2. The Details
### User stories
- As a Wanderer, I want to see a few hand-picked titles as soon as I open the app, so that I can find something worth watching without scrolling through the whole catalogue.
- As a Wanderer, I want to start a pick in one tap, so that I'm watching before I lose interest.
- As a curator, I want to set and reorder the Spotlight picks myself, so that the rail stays fresh without waiting for engineering.
- As a product manager, I want every play that starts from Spotlight to be tracked by segment until it reaches 30 minutes, so that I can measure the Wanderer watch-through rate and make the go/no-go call.
### Screens to build
- Entry point: Home with Spotlight rail. The rail sits at the top, above Trending, with about 5 curated picks. A "Curator mode" toggle opens a side panel where curators add, remove and reorder picks. It's a panel on this screen, not a separate screen.
- Feature core: Spotlight player. A pick opens straight into a simulated player with a progress bar, a "watched minutes" counter and an exit button.
- Success / confirmation: watch-through confirmed. Shown when a session reaches 30 minutes. It displays a "You watched [title]" message and a small metrics panel with Spotlight plays, plays that reached 30+ minutes, and the watch-through rate, by segment.
### Functional requirements
- Curators can add, remove and reorder picks in Curator mode, and the rail updates immediately.
- The rail holds at least 1 and at most 5 picks. Curators can't add a sixth or save an empty rail.
- Every play started from the rail is logged as a Spotlight play, with the title, the segment (Wanderer, Casual or Power User) and the start time.
- A play is counted as a watch-through when it reaches 30 minutes of watched time.
- A session that ends before 30 minutes stays logged as a Spotlight play, not a watch-through.
- Watch-through rate = Spotlight watch-throughs ÷ Spotlight plays, shown per segment and updated in real time.
- Plays started from anywhere other than the rail, such as the Trending rows, aren't counted in Spotlight metrics.
- A play starts in one tap from a rail card, with no detail page in between.
### Smart behaviors (Situation → Outcome)
- If the curator removes every pick → keep the last pick and show "The rail needs at least one pick."
- If the curator tries to add a sixth pick → block it and show "Spotlight is capped at 5 picks."
- If the user has already watched a pick to the end → hide it from their rail.
- If the user exits the player before 30 minutes → log a Spotlight play without a watch-through, and return them to Home.
- If a session reaches 30 minutes → log a watch-through and show the confirmation screen.
- If the segment is set to Power User → show the rail as normal, but keep their metrics separate, to protect the guardrail.
- If the user is in the holdout group → hide the rail and show the Full Library home, and log nothing to Spotlight metrics.
- If a pick is focused or hovered → don't play a trailer automatically.
### Technical constraints
- A single-file React prototype. Use useState for all state, with no Redux and no Context.
- No APIs, no backend, no database and no authentication.
- No localStorage or persistence; everything resets on reload.
- Hard-code mock data: about 15 titles, each with a title, genre, length and poster colour block, rather than real images.
- No real video. The player is a simulated timer at accelerated speed, 1 second = 1 minute, so 30 minutes takes 30 seconds.
- No analytics SDK. Keep events in an in-memory log that the metrics panel reads.
- No curation CMS. Curator mode is a local panel in the prototype.
- Use a segment switcher (Wanderer, Casual or Power User) and a holdout toggle to simulate different users, rather than real user profiles.
- Don't build A2 labels, mood filters, badges or personalisation. They're out of scope.

## 3. The Logistics
### Features out
- Algorithmic ordering or personalisation of the rail. Curators decide the order. It contradicts the human-curation strategy, and Wanderers have too little viewing history to personalise from.
- More than one Spotlight rail. A single rail with at most 5 picks. Several rails would bring back the choice overload the feature exists to remove.
- Putting the rail behind the premium tier for Wanderers. It's free for every subscriber in the test. A paywall would stop the target persona from ever reaching the fix.
### Edge cases & safety guard
- Unhappy paths:
- Every pick has already been watched → show the next unwatched curated titles from the curator's list. If none are left, show "New picks arrive this week" rather than an empty rail.
- A curator removes a title while someone is watching it → let the session finish and log it as normal. The rail updates once the user returns to Home.
- The user exits at 29 minutes → log a Spotlight play, not a watch-through. Don't round up.
- The user pauses → stop the timer. Only time actually watched counts towards the 30 minutes.
- The same title is started from Spotlight and from Trending → log only the Spotlight play as Spotlight.
- The user replays the same pick → log a new play each time. A session can be counted as a watch-through only once.
- The segment or the holdout setting changes mid-session → the session keeps the segment and group it started with.
- What it must NEVER do:
- Show more than 5 picks, or an empty rail.
- Reorder picks automatically.
- Show the rail to anyone in the holdout group.
- Count a session as a watch-through before 30 minutes of watched time.
- Count plays from outside the rail in Spotlight metrics.
- Play trailers automatically on the rail.
- Lock the rail behind premium for Wanderers.
### Decision log
- 3. Decision log
- Decision	Alternative rejected	Why
- Curation is a configuration panel inside the prototype, not a full CMS	A separate curator tool with roles, scheduling and approvals	The Must Have only needs curators to be able to set picks. A CMS would use most of the sprint and does nothing for the Wanderer's friction.
- Playback is simulated (1 second = 1 minute), and tracking is an in-memory event log	Real video streaming and an analytics SDK	The prototype has to prove the flow from rail to watch-through and the metric logic, not the streaming infrastructure. Simulating it means the 30-minute rule can be tested in 30 seconds, with no APIs or database.
### Evals
- 4. Evals
- Eval	Target	How to measure
- % accuracy (tracking)	100% of simulated sessions are logged correctly: Spotlight play vs. watch-through, right segment, no double counts	Run a scripted set of 20 sessions, mixing exits before 30 minutes, completions, pauses and plays from Trending, then compare the metrics panel with the expected results.
- Time-on-task (persona)	A Wanderer goes from Home to starting a pick in under 30 seconds, against the 20 minutes in the moment of misery	Run moderated tests with 5 or more testers playing the Wanderer, timed from Home loading to pressing play.
- Safety	0 breaches of the "must NEVER" list across all test sessions	Before sign-off, check each rule in the "must NEVER" list (rail size, holdout, autoplay, counting rules) and confirm none of them was broken.

## MoSCoW scope
- **Must:** Show a fixed, short set of picks.; Curators can set the picks.; Watch-through tracking: tag plays that start from Spotlight and record whether they reach 30 minutes, broken down by segment
- **Should:** Put the rail at the top of the home screen, above Trending.; Already-watched titles hidden from the rail.; Autoplay trailers switched off on the rail.
- **Could:** A curator tool that doesn't depend on engineers; A "New this week"; Save to My List from the rail
- **Won't (now):** Algorithmic ordering or personalisation of the rail; More than one Spotlight rail; Putting the rail behind the premium tier for Wanderers

---
**Builder hook:** Build a working prototype based on this PRD. Use the User Story as the core flow, Functional Requirements as build constraints, and prioritize speed and clarity over visual complexity.
