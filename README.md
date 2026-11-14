# Kuasar Crew Health

A visual self-assessment tool that helps astronauts check their own health during a space mission and tells them what to do next.

Built by team **Kuasar Selçuklu** for the 2026 NASA Space Apps Challenge.

## What it does

The page is split into tabs: Overview, Check-in, Body map, Trends, Radiation, Morale and Sources. The status banner stays above the tabs, and a small mark on a tab shows when something there needs attention. Each tab has its own link (for example `#radiation`).


- **Body map:** a clickable astronaut figure. Each region shows its status by color and symbol.
- **Daily check-in:** blood pressure, heart rate, blood oxygen, blood carbon dioxide, blood glucose, body temperature, sleep, mood, optic nerve sheath diameter, exercise, cabin carbon dioxide and daily radiation dose.
- **Guidance:** every reading shows its reference range, what its unit means, step-by-step measurement instructions, and what to do when it is out of range.
- **Escalation:** tells the astronaut when to inform the crew medical officer and when to contact the flight surgeon, including the signal delay to Earth.
- **Onboard assistant:** a rule-based helper that runs fully offline. It learns each astronaut's personal baseline from earlier check-ins, flags readings that are unusual for that person, interprets readings together (for example fever with a fast pulse), tolerates typos, and can be taught crew notes. It answers questions about the logged readings and gives understands a body part together with a symptom ("my heart aches"), finds the closest topic when no phrase matches, and gives first-response steps for 54 likely health and technical problems, such as headache, nausea, fire, cabin pressure loss and power loss.
- **Weekly morale survey:** opens in its own window with a progress bar. 12 questions on a 1 to 5 scale give four sub-scores (mood and stress, physical and cognitive, social and crew, isolation) and a General Psychological Risk Index from 12 to 60. Green is 12 to 25, Yellow 26 to 40, Red 41 to 60. Constant irritability, intense anxiety or serious crew conflict set the level to Red whatever the total. Two open questions are logged but not scored. Past results are listed in a history table, answers can be cleared before submitting, and the whole survey history can be reset after an on-page confirmation. The index was designed by the team and is not a validated clinical instrument.
- **Environments:** ISS, Moon base, Mars base and Mars transit, each with its own gravity, signal delay and expected radiation dose.
- **Daily and weekly goals:** shown right under the status banner. Daily goals: log the check-in, sleep 7 to 9 h, exercise 60 min or more, every reading in range. Weekly goals per mission week: check in every day, 600 min of exercise (the station average from NASA OCHMO-TB-031), 7 to 9 h sleep on 5 nights, every daily goal on 5 days, and the morale survey. Daily and weekly streaks count how many days and weeks in a row every goal was met.
- **Trends:** a chart for each indicator.
- **Cumulative radiation dose:** this mission's dosimeter readings plus the dose from earlier missions, against NASA's 600 mSv career limit. The tool warns at 300 mSv (half of the limit), asks for action at 480 mSv (80%) and raises an alert when the limit is reached, in the dose panel, the status banner and the assistant.
- **Sleep:** 7 to 9 hours is the target. More than 9 hours is flagged, more than 11 hours needs action, and repeated long nights are pointed out by the assistant.

## How to run

Open `index.html` in any modern browser. No installation or server is needed.

## NASA data and resources used

- [NASA Human Research Program, 5 Hazards of Human Spaceflight](https://www.nasa.gov/hrp/hazards): the hazard model behind every body region.
- [NASA, The Human Body in Space](https://www.nasa.gov/humans-in-space/the-human-body-in-space/): bone loss of 1% to 1.5% per month, one-way signal delay of up to 20 minutes from Mars.
- [NASA OCHMO-TB-004, Carbon Dioxide](https://www.nasa.gov/wp-content/uploads/2023/12/ochmo-tb-004-carbon-dioxide.pdf): cabin CO2 limit of 3 mmHg as a 1-hour average (NASA-STD-3001 [V2 6004]).
- [NASA OCHMO Radiation Protection technical brief](https://www.nasa.gov/wp-content/uploads/2023/03/radiation-protection-technical-brief-ochmo.pdf): 600 mSv career limit, 250 mSv per solar particle event, about 1.5 mSv per day in Mars transit.
- [NASA OCHMO-TB-031, Exercise Overview](https://www.nasa.gov/wp-content/uploads/2023/12/ochmo-tb-031-exercise-overview.pdf): about 600 minutes of exercise per week on the station.

Other reference: [Optic nerve sheath diameter and spaceflight, npj Microgravity 2022](https://pmc.ncbi.nlm.nih.gov/articles/PMC9537149).

## Tools and other resources

- [WebLLM](https://github.com/mlc-ai/web-llm) 0.2.84 by MLC AI (Apache-2.0 license): runs the optional language model in the browser.
- Llama 3.2 1B Instruct by Meta (Llama 3.2 Community License): the optional language model, downloaded only when the user asks for it. If it is not available, WebLLM's Qwen2.5 or SmolLM2 models are used instead.
- [IBM Plex Sans and IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Sans) fonts (SIL Open Font License), loaded from Google Fonts.
- Claude by Anthropic: AI assistance for writing the code.

Values still to be confirmed against NASA sources: expected daily dose for the ISS (0.5 mSv), the lunar surface (1.4 mSv) and the Mars surface (0.64 mSv), and the general adult clinical ranges for blood pressure, heart rate, blood oxygen, blood CO2, glucose, temperature and sleep.

## Limits of this prototype

- Reference ranges are general adult clinical ranges used as placeholders.
- Reports to the crew and to the ground are simulated. Nothing is transmitted.
- The page opens with clearly labeled example data.
- This is not a medical device.

## Optional on-device AI model

The assistant works without any AI model. On request ("Load AI model" in the assistant window) the page loads the open-source [WebLLM](https://github.com/mlc-ai/web-llm) library and an open language model (for example Llama 3.2 1B Instruct), downloads it once and runs it in the browser through WebGPU. No server or API key is used. The model receives the astronaut's logged readings, reference ranges, the assistant's insights and the matching procedure notes, and its answers are labeled in the chat. If the model is missing or fails, the rule-based answer is shown instead. It needs a recent Chrome or Edge on a computer with WebGPU.

## Use of AI

The code in this repository was generated with the assistance of an AI large language model (Claude, by Anthropic), directed and reviewed by the team. The project concept and design decisions are the team's own. No NASA branding is used.

## Tools

HTML, CSS and JavaScript in a single file. No external libraries.
