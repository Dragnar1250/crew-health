# Kuasar Crew Health

A visual self-assessment tool that helps astronauts check their own health during a space mission and tells them what to do next.

Built by team **Kuasar Selçuklu** for the 2026 NASA Space Apps Challenge.

## What it does

The page is split into tabs: Overview, Check-in, Body map, Trends, Radiation, Morale, Med kit and Sources. The status banner stays above the tabs, and a small mark on a tab shows when something there needs attention. Each tab has its own link (for example `#radiation`).


- **Body map:** a clickable astronaut figure. Each region shows its status by color and symbol.
- **Daily check-in:** blood pressure, heart rate, blood oxygen, blood carbon dioxide, blood glucose, body temperature, sleep, mood, optic nerve sheath diameter, exercise, cabin carbon dioxide and daily radiation dose.
- **Guidance:** every reading shows its reference range, what its unit means, step-by-step measurement instructions, and what to do when it is out of range.
- **Escalation:** tells the astronaut when to inform the crew medical officer and when to contact the flight surgeon, including the signal delay to Earth.
- **Onboard assistant:** a rule-based helper that runs fully offline. It learns each astronaut's personal baseline from earlier check-ins, flags readings that are unusual for that person, interprets readings together (for example fever with a fast pulse), tolerates typos, and can be taught crew notes. It answers questions about the logged readings and gives understands a body part together with a symptom ("my heart aches"), finds the closest topic when no phrase matches, and gives first-response steps for 54 likely health and technical problems, such as headache, nausea, fire, cabin pressure loss and power loss.
- **Weekly morale survey:** opens in its own window with a progress bar. 12 questions on a 1 to 5 scale give four sub-scores (mood and stress, physical and cognitive, social and crew, isolation) and a General Psychological Risk Index from 12 to 60. Green is 12 to 25, Yellow 26 to 40, Red 41 to 60. Constant irritability, intense anxiety or serious crew conflict set the level to Red whatever the total. Two open questions are logged but not scored. Past results are listed in a history table, answers can be cleared before submitting, and the whole survey history can be reset after an on-page confirmation. The index was designed by the team and is not a validated clinical instrument.
- **Medical kit:** medicines and supplies with stock, minimum, pack and expiry date, following NASA-STD-3001 [V2 7059] inventory tracking. Items that are expired, out of stock, below their minimum or expiring within 30 days are flagged on the tab, in the overview and by the assistant. Every use is logged, and a check-in can count the test supplies it uses (1 glucose strip, 2 lancets, 1 analyzer cartridge). The example kit uses medicine names from NASA's pharmaceuticals brief; amounts and dates are invented, and the tool gives no medicine doses.
- **Environments:** ISS, Moon base, Mars base and Mars transit, each with its own gravity, signal delay and expected radiation dose.
- **Daily and weekly goals:** shown right under the status banner. Daily goals: log the check-in, sleep 7 to 9 h, exercise 60 min or more, every reading in range. Weekly goals per mission week: check in every day, 600 min of exercise (the station average from NASA OCHMO-TB-031), 7 to 9 h sleep on 5 nights, every daily goal on 5 days, and the morale survey. Daily and weekly streaks count how many days and weeks in a row every goal was met.
- **Trends:** a chart for each indicator.
- **Cumulative radiation dose:** this mission's dosimeter readings plus the dose from earlier missions, against NASA's 600 mSv career limit. The tool warns at 300 mSv (half of the limit), asks for action at 480 mSv (80%) and raises an alert when the limit is reached, in the dose panel, the status banner and the assistant.
- **Sleep:** 7 to 9 hours is the target. More than 9 hours is flagged, more than 11 hours needs action, and repeated long nights are pointed out by the assistant.

## How to run

Open `index.html` in any modern browser. No installation or server is needed.

## NASA data and resources used

- [NASA HRP, 5 Hazards of Human Spaceflight](https://www.nasa.gov/hrp/hazards): the hazard model behind every body region.
- [NASA, The Human Body in Space](https://www.nasa.gov/humans-in-space/the-human-body-in-space/): bone loss of 1% to 1.5% per month, signal delay of up to 20 minutes from Mars.
- [NASA OCHMO-TB-004, Carbon Dioxide](https://www.nasa.gov/wp-content/uploads/2023/12/ochmo-tb-004-carbon-dioxide.pdf): cabin CO2 limit of 3 mmHg as a 1-hour average (NASA-STD-3001 [V2 6004]).
- [NASA OCHMO Radiation Protection technical brief](https://www.nasa.gov/wp-content/uploads/2023/03/radiation-protection-technical-brief-ochmo.pdf): 600 mSv career limit, 250 mSv per solar particle event.
- [NASA, Space Faring: The Radiation Challenge](https://www.nasa.gov/wp-content/uploads/2017/04/radiationchallenge.pdf): 80 to 160 mSv for a six-month ISS stay (0.66 mSv per day used), about 2 mSv per year natural background, sievert, gray and rem.
- [NASA JPL, Curiosity RAD measurements](https://www.jpl.nasa.gov/images/pia17600-radiation-measurements-on-mars/): 0.64 mSv per day on the Mars surface (Hassler et al., Science, 2014) and 1.84 mSv per day in cruise (Zeitlin et al., Science, 2013).
- [NASA OCHMO-TB-031, Exercise Overview](https://www.nasa.gov/wp-content/uploads/2023/12/ochmo-tb-031-exercise-overview.pdf): about 600 minutes of exercise per week on the station.
- [NASA OCHMO Sleep Accommodations brief](https://www.nasa.gov/wp-content/uploads/2023/03/sleep-accomodations-technical-brief-ochmo.pdf): 7 to 9 hours needed, 6 to 6.5 hours measured on the ISS.
- [NASA OCHMO-TB-006, Pharmaceuticals](https://www.nasa.gov/wp-content/uploads/2023/12/ochmo-tb-006-pharmaceuticals.pdf): inventory tracking requirement [V2 7059], ISS kit packs, 1 to 2 year expiration against 1 to 5 year missions, the Dose Tracker study, formulary medicines.

Other spaceflight research: [Zhang et al., Science Advances, 2020](https://www.sci.news/space/radiation-dose-rates-lunar-surface-08893.html) (1.369 mSv per day on the lunar surface) and [Optic nerve sheath diameter and spaceflight, npj Microgravity, 2022](https://pmc.ncbi.nlm.nih.gov/articles/PMC9537149).

Clinical reference ranges: [American Heart Association, blood pressure](https://www.heart.org/bplevels), [Mayo Clinic, resting heart rate](https://www.mayoclinic.org/healthy-lifestyle/fitness/expert-answers/heart-rate/faq-20057979), [MedlinePlus, pulse oximeters](https://magazine.medlineplus.gov/pdf/Pulse_oximeters.PDF_.final_.011123.pdf), [MedlinePlus, blood gases](https://medlineplus.gov/ency/article/003855.htm), [American Diabetes Association, hypoglycemia classification](https://ada.silverchair.com/view-large/3051584), [CDC, fever definition](https://www.cdc.gov/port-health/php/definitions-symptoms-reportable-illness/index.html).

## Tools and other resources

- [WebLLM](https://github.com/mlc-ai/web-llm) 0.2.84 by MLC AI (Apache-2.0 license): runs the optional language model in the browser.
- Llama 3.2 1B Instruct by Meta (Llama 3.2 Community License): the optional language model, downloaded only when the user asks for it. If it is not available, WebLLM's Qwen2.5 or SmolLM2 models are used instead.
- [IBM Plex Sans and IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Sans) fonts (SIL Open Font License), loaded from Google Fonts.
- Claude by Anthropic: AI assistance for writing the code.

The "Act now" thresholds and the dose warning steps are the team's own proposal; the sources above set the normal ranges and limits.

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
