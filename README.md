# Kuasar Crew Health

A visual self-assessment tool that helps astronauts check their own health during a space mission and tells them what to do next.

Built by team **Kuasar Selçuklu** for the 2026 NASA Space Apps Challenge.

## What it does

- **Body map:** a clickable astronaut figure. Each region shows its status by color and symbol.
- **Daily check-in:** blood pressure, heart rate, blood oxygen, blood carbon dioxide, blood glucose, body temperature, sleep, mood, optic nerve sheath diameter, exercise and daily radiation dose.
- **Guidance:** every reading shows its reference range, how to measure it, and what to do when it is out of range.
- **Escalation:** tells the astronaut when to inform the crew medical officer and when to contact the flight surgeon, including the signal delay to Earth.
- **Onboard assistant:** a rule-based helper that runs fully offline. It learns each astronaut's personal baseline from earlier check-ins, flags readings that are unusual for that person, interprets readings together (for example fever with a fast pulse), tolerates typos, and can be taught crew notes. It answers questions about the logged readings and gives first-response steps for 36 likely health and technical problems, such as headache, nausea, fire, cabin pressure loss and power loss.
- **Environments:** ISS, Moon base and Mars base, each with its own gravity, signal delay and expected radiation dose.
- **Trends and routine:** a chart for each indicator, streak badges and a cumulative radiation dose bar.

## How to run

Open `index.html` in any modern browser. No installation or server is needed.

## Limits of this prototype

- Reference ranges are general adult clinical ranges used as placeholders.
- Reports to the crew and to the ground are simulated. Nothing is transmitted.
- The page opens with clearly labeled example data.
- This is not a medical device.

## Use of AI

The code in this repository was generated with the assistance of an AI large language model (Claude, by Anthropic), directed and reviewed by the team. The project concept and design decisions are the team's own. No NASA branding is used.

## Tools

HTML, CSS and JavaScript in a single file. No external libraries.
