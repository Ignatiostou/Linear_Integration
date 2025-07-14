# Linear_Integration

📅 Sports Team Scheduler with Broadcasting & Venue Constraints
This project generates an optimal round-robin match schedule for a group of professional football teams, subject to broadcasting rights, shared stadium constraints, and scheduling fairness (minimizing home/away "breaks"). The program outputs a valid fixture list and exports it to Excel, along with an interactive GUI for easy viewing.

🚀 Features
⚖️ Fair scheduling: Ensures each team plays an equal number of home and away matches in each half of the season, minimizing schedule breaks.

📺 Broadcasting constraints: Teams assigned to two broadcasters (COSMOTE and NOVA) are scheduled so both networks receive balanced weekly coverage.

🏟️ Stadium sharing: Teams that share a stadium never play home games in the same round.

🔁 Repeated attempts: The algorithm iteratively searches for a feasible solution (up to 100 tries).

📊 Excel export: Outputs a structured fixture table and constraint checks to an Excel file.

🖥️ Graphical interface: Displays the weekly schedule interactively using tkinter.

🧠 Optimization Logic
The program is implemented in Python using:

pulp: Linear programming solver

pandas: For Excel export

tkinter: For GUI visualization

itertools, random, and standard libraries

It works in 3 phases:

Pattern Generation & Selection

Generate feasible home/away patterns that avoid 3 consecutive games of the same type (HHH or AAA).

Select patterns for COSMOTE and NOVA teams such that they meet weekly balancing constraints.

Pattern Matching

Form a complete round-robin match schedule by matching compatible Home vs Away patterns.

Ensure each pair of patterns meets exactly twice (once home, once away).

Team Assignment

Assign each team to a pattern while:

Respecting channel rights.

Avoiding stadium conflicts.

Ensuring seeded teams don’t play each other in the first/last round if not allowed.

🏁 Output
🗂️ Excel File: τελικό_πρόγραμμα.xlsx

Sheet Πρόγραμμα: Tabular match schedule

Sheet Έλεγχοι: Verifications (e.g., if all pairs play, any 3-HHH sequences)

🖼️ GUI Viewer:

Tabbed window showing matches for each week

Includes channel information for each match

📦 Requirements
Install required dependencies with:

bash
Αντιγραφή
Επεξεργασία
pip install pulp pandas xlsxwriter
▶️ How to Run
Simply run the main Python script:

bash
Αντιγραφή
Επεξεργασία
python final_football_schedule.py
The program will:

Attempt to find a feasible schedule.

Print results in the terminal.

Export the final schedule to Excel.

Launch the GUI.

📝 Teams Used
Includes top teams across Europe:

COSMOTE: Barcelona, Real Madrid, Man City, Liverpool, etc.

NOVA: Milan, Inter, AEK, Panathinaikos, etc.

Some teams share stadiums (e.g., Inter & Milan), and these constraints are enforced in scheduling.

🛠️ Customization
You can customize:

teams, cosmote_teams, nova_teams

shared_stadium_pairs

seeded_teams

...to reflect different league rules or broadcasting rights.

📄 License
This project is open-source under the MIT License.
