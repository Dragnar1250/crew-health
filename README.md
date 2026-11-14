# Kuasar Crew Health

A visual self-assessment tool that helps astronauts check their own health during a space mission and tells them what to do next.

Built by team **Kuasar Selçuklu** for the 2026 NASA Space Apps Challenge.

## What it does

The page is split into tabs: Overview, Report, Check-in, Live, Analysis, Performance, Body map, Trends, Radiation, Morale, Med kit and Sources. An EN / TR button in the header switches the whole interface between English and Turkish; the choice is remembered on the device. The status banner stays above the tabs, and a small mark on a tab shows when something there needs attention. Each tab has its own link (for example `#radiation`).


- **Body map:** a clickable astronaut figure. Each region shows its status by color and symbol.
- **Daily check-in:** blood pressure, heart rate, blood oxygen, blood carbon dioxide, blood glucose, body temperature, sleep, mood, optic nerve sheath diameter, exercise, cabin carbon dioxide and daily radiation dose.
- **Crew profile:** age, height, body mass and sex. The profile sets the personal fluid target (32 mL per kg of body mass, at least 2.5 L for men and 2.1 L for women), the daily energy need (NASA equation), the body mass index, the estimated maximum heart rate (220 minus age) and the exercise heart rate zones. A table shows which readings the profile changes and which it does not: NASA's career radiation limit, for example, is the same for every age and sex.
- **Water tracker:** quick buttons (+100, +250, +500 mL or any amount) with a progress bar against the personal target, a pace mark spread over the waking hours of the light plan, a log with undo, and a chart of the last 7 days. The total is filled in as the fluid intake of the next check-in.
- **General health report and score:** a score from 0 to 100 with grades A to E, built from the body systems score (45%), performance risk (20%), the 7-day routine for sleep, exercise and fluid (20%), morale (10%) and the unused share of the career radiation limit (5%). It is capped at 69 while a reading needs action and at 49 while an extreme situation is detected. The report lists the profile, every body system, 7-day averages against targets, findings and recommended next steps, and can be copied as text.
- **Mind and performance:** daily mood (1 to 5), stress level (0 to 10), reaction time and attention lapses from the reaction test, plus fluid intake and back pain.
- **More health data:** breathing rate, and six self-rated symptoms from 0 (none) to 3 (severe): cough, shortness of breath, headache, nausea, dizziness and blurred vision. The check-in also asks whether there was a spacewalk or surface excursion that day.
- **Health analysis (Analysis tab):**
  - *Combined check:* every reading is compared with the crew member's own mean and spread, and the sum of squared distances is tested with a chi-square distribution, so several small changes on the same day are noticed together.
  - *Problems across several readings:* 15 rules (for example slower thinking from fatigue or stress, infection, low oxygen, CO2 build-up, dehydration, radiation sickness, decompression sickness) fire only when at least two readings point the same way, and each lists possible causes and what to do.
  - *Why is a reading off?* For every reading that is out of range or unusual, the possible causes are checked against the other readings, excursions, the environment, the morale survey and the medicine log, and marked as supported, ruled out or not checkable.
  - *Extreme situation checks:* 14 checks (solar particle event, cabin pressure loss, CO2 removal failure, fire or toxic air, infectious illness, heat injury, hypothermia, severe low blood sugar, cardiac emergency, decompression sickness, acute radiation sickness, raised pressure behind the eyes, severe sleep deprivation, psychological crisis). Each has a Test button that loads simulated readings, so the whole tool can be seen reacting. Simulated readings are never saved.
- **Live telemetry (simulation mode):** simulated wearable sensors stream heart rate, blood oxygen, body temperature and breathing rate once a second as live charts. Events (fast heart rate, oxygen drop, fever) can be injected; a reading out of range for 5 seconds raises a sensor alert. The last 30 seconds can be copied into the check-in. A hypnogram shows last night's sleep stages, simulated from the logged sleep length.
- **Performance risk and early warning:** a score from 0 to 100 built from sleep debt, short sleep, stress, low mood, isolation, slower reactions, attention lapses, high CO2 and low fluid intake, with the factors behind it, actions, and a 3-day trend forecast that warns before the risk reaches the next level. Based on NASA's risk of performance decrements from sleep loss and circadian desynchronization; the weights are the team's proposal.
- **Reaction test:** a short psychomotor vigilance test (10 trials, false starts detected). Responses of 355 ms or more count as attention lapses (Jones et al., Sleep, 2022). The median and lapses can be saved to the check-in.
- **Circadian light plan and sleep hygiene:** a 24-hour plan for the ISS-style general, blue-enriched and pre-sleep light settings from the planned sleep and wake times, and sleep tips ranked for the day's data.
- **Targeted advice:** each flagged body region gets specific steps, for example a knees-to-chest stretch for lower back tension or drinking more when fluid intake is low.
- **Visual overview:** a radar chart of body systems, a performance gauge and a heat map of every body system over the last 14 days.
- **Guidance:** every reading shows its reference range, what its unit means, step-by-step measurement instructions, and what to do when it is out of range.
- **Escalation:** tells the astronaut when to inform the crew medical officer and when to contact the flight surgeon, including the signal delay to Earth.
- **Weekly morale survey:** opens in its own window with a progress bar. 12 questions on a 1 to 5 scale give four sub-scores (mood and stress, physical and cognitive, social and crew, isolation) and a General Psychological Risk Index from 12 to 60. Green is 12 to 25, Yellow 26 to 40, Red 41 to 60. Constant irritability, intense anxiety or serious crew conflict set the level to Red whatever the total. Two open questions are logged but not scored. Past results are listed in a history table, answers can be cleared before submitting, and the whole survey history can be reset after an on-page confirmation. The index was designed by the team and is not a validated clinical instrument.
- **Medical kit:** a "What needs attention" list at the top explains in plain sentences what is expired, running low or expiring soon, with a button to fix it. Medicines and supplies are listed separately with what each one is for, a stock bar against its minimum and a readable expiry date. "Took 1" or "Used 1" logs a use, and "Restock" opens the form already filled in. The kit tracks stock, minimum, pack and expiry date, following NASA-STD-3001 [V2 7059] inventory tracking. Items that are expired, out of stock, below their minimum or expiring within 30 days are flagged on the tab and in the overview, and the analysis uses the medicine log when it looks for causes. Every use is logged, and a check-in can count the test supplies it uses (1 glucose strip, 2 lancets, 1 analyzer cartridge). The example kit uses medicine names from NASA's pharmaceuticals brief; amounts and dates are invented, and the tool gives no medicine doses.
- **Environments:** ISS, Moon base, Mars base and Mars transit, each with its own gravity, signal delay and expected radiation dose.
- **Daily and weekly goals:** shown right under the status banner. Daily goals: log the check-in, sleep 7 to 9 h, exercise 60 min or more, drink the fluid target, every reading in range. Weekly goals per mission week: check in every day, 600 min of exercise (the station average from NASA OCHMO-TB-031), 7 to 9 h sleep on 5 nights, every daily goal on 5 days, and the morale survey. Daily and weekly streaks count how many days and weeks in a row every goal was met.
- **Trends:** a chart for each indicator.
- **Cumulative radiation dose:** this mission's dosimeter readings plus the dose from earlier missions, against NASA's 600 mSv career limit. The tool warns at 300 mSv (half of the limit), asks for action at 480 mSv (80%) and raises an alert when the limit is reached, in the dose panel, the status banner and the analysis.
- **Sleep:** 7 to 9 hours is the target. More than 9 hours is flagged, more than 11 hours needs action, and repeated long nights are pointed out in the overview.

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
- [NASA, Risk of performance decrements from sleep loss, circadian desynchronization and work overload](https://www.nasa.gov/directorates/esdmd/hhp/risk-of-performance-decrements-and-adverse-health-outcomes-resulting-from-sleep-loss-circadian-desynchronization-and-work-overload): the risk behind the performance score.
- [NASA OCHMO Water technical brief](https://www.nasa.gov/wp-content/uploads/2023/03/water-technical-brief-ochmo.pdf): at least 2.5 L of drinking water per crew member per day (NASA-STD-3001 [V2 6109]).
- [NASA JSC-67378, Nutritional Requirements for Exploration Missions](https://ntrs.nasa.gov/api/citations/20205008306/downloads/JSC67378%20Expl%20Nutr%20Reqs%20042020.pdf): energy need from age, body mass, height and sex; fluid intake of 32 mL per kg per day, at least 2.5 L for men and 2.1 L for women.

Other studies used for the new features: [Human Performance Resource Center, heart rate zones](https://www.hprc-online.org/physical-fitness/training-performance/how-train-using-heart-rate-zones) (220 minus age, CDC zones of 64% to 76% and 77% to 93%), [WHO, body mass index](https://www.who.int/news-room/fact-sheets/detail/obesity-and-overweight), [Jones et al., Sleep, 2022](https://pmc.ncbi.nlm.nih.gov/articles/PMC8919197) (ISS Reaction Self Test, 355 ms lapse threshold), [Anesthesiology, Back Pain in Outer Space](https://asa2.silverchair.com/anesthesiology/article/135/3/384/115740/Back-Pain-in-Outer-Space) (knees-to-chest relief), [Space.com, ISS LED lighting](https://www.space.com/35997-led-lights-help-astronauts-sleep-better.html), [MedlinePlus, vital signs](https://medlineplus.gov/ency/article/002341.htm) (breathing rate 12 to 18).

Other spaceflight research: [Zhang et al., Science Advances, 2020](https://www.sci.news/space/radiation-dose-rates-lunar-surface-08893.html) (1.369 mSv per day on the lunar surface) and [Optic nerve sheath diameter and spaceflight, npj Microgravity, 2022](https://pmc.ncbi.nlm.nih.gov/articles/PMC9537149).

Clinical reference ranges: [American Heart Association, blood pressure](https://www.heart.org/bplevels), [Mayo Clinic, resting heart rate](https://www.mayoclinic.org/healthy-lifestyle/fitness/expert-answers/heart-rate/faq-20057979), [MedlinePlus, pulse oximeters](https://magazine.medlineplus.gov/pdf/Pulse_oximeters.PDF_.final_.011123.pdf), [MedlinePlus, blood gases](https://medlineplus.gov/ency/article/003855.htm), [American Diabetes Association, hypoglycemia classification](https://ada.silverchair.com/view-large/3051584), [CDC, fever definition](https://www.cdc.gov/port-health/php/definitions-symptoms-reportable-illness/index.html).

## Tools and other resources

- [IBM Plex Sans and IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Sans) fonts (SIL Open Font License), loaded from Google Fonts.
- Claude by Anthropic: AI assistance for writing the code.

The "Act now" thresholds, the dose warning steps, the performance risk score and the general health score with its weights are the team's own proposal; the sources above set the normal ranges and limits.

## Limits of this prototype

- Reference ranges are general adult clinical ranges used as placeholders.
- Live telemetry and sleep stages are simulated; a flight version would read real wearable sensors.
- The Turkish interface is for the team; the English interface is the one for judging.
- Reports to the crew and to the ground are simulated. Nothing is transmitted.
- The page opens with clearly labeled example data.
- This is not a medical device.

## Use of AI

The code in this repository was generated with the assistance of an AI large language model (Claude, by Anthropic), directed and reviewed by the team. The project concept and design decisions are the team's own. No NASA branding is used.

## Tools

HTML, CSS and JavaScript in a single file. No external libraries.
