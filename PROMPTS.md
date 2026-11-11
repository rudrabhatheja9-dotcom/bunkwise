Build BunkWise, a single-file web app (HTML, CSS and vanilla JavaScript, no frameworks) for college students who need to maintain 75% attendance.

PROBLEM
Students lose track of attendance across subjects and only find out they are short when it is too late. Counting "how many classes can I still skip?" by hand is slow and error-prone.

CORE FEATURES
- Add subjects with classes attended and total classes held
- Show attendance % per subject with a progress bar that marks the required cutoff
- Tell the student either "You can skip N classes and stay above the target" or "Attend the next N classes in a row to recover"
- A what-if slider (0 to 10) that shows the projected % if they skip the next few classes
- One-tap "Attended class" and "Missed class" buttons
- An overall "bunk budget" number at the top: the total spare classes across all subjects that are at or above the target
- An adjustable required attendance percentage (50 to 95, default 75)
- A delete button for each subject

DESIGN
- Colour-coded status: safe, borderline (1 or fewer spare classes) and below target
- A distinctive, bold heading font with a clean system font for body text
- The bunk budget number is the hero element at the top of the page
- Mobile-first and responsive
- Light and dark mode through prefers-color-scheme
- Visible keyboard focus, accessible colour contrast, and reduced-motion support
- A friendly empty state when there are no subjects

TECHNICAL REQUIREMENTS
- Everything in one index.html file
- Save data in localStorage inside try/catch, and pre-load three sample subjects on first visit
- Validate that attended classes cannot exceed total classes
- Escape user input before putting it in the page
- Use these formulas:
  - Classes you can skip = floor(attended / target - total)
  - Classes needed to recover = ceil((target * total - attended) / (1 - target)), where target is a fraction
