# BunkWise: Attendance Guardian

**Live demo:** https://rudrabhatheja9-dotcom.github.io/bunkwise/

## The problem
Students lose track of attendance across subjects and only find out they are short when it is too late. Counting "how many can I still skip?" by hand is slow and easy to get wrong.

## The solution
BunkWise turns your attendance numbers into a clear answer for every subject:
- Attendance % with a bar that marks your required cutoff
- "You can skip N classes" or "Attend the next N classes in a row to recover"
- A what-if slider that shows your % if you skip the next few classes
- One-tap logging for "Attended class" and "Missed class"
- A bunk budget that adds up the spare classes across all safe subjects
- Adjustable required attendance (50 to 95%), saved in your browser

## Tech stack
HTML, CSS and vanilla JavaScript in a single file. Data is saved in the browser with `localStorage`. No install, no backend.

## Run it locally
Open `index.html` in any browser.

## How the maths works
- Classes you can skip: `floor(attended / target - total)`
- Classes needed to recover: `ceil((target * total - attended) / (1 - target))`

## Built with AI
Designed and built with Claude using prompt-driven development. See `PROMPTS.md` for the prompts used.

## Future scope
Timetable import, reminders before low-attendance days, per-semester history and sharing with a parent or mentor.
