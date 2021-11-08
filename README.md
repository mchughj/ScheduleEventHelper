
# Schedule Event Helper

This is a simple project which made it easy to create the teams for a 100+ person soccer event.

1. Install necessary prerequisites
   ```
   sudo apt install -y python3
   python3 -m pip install --user --upgrade pip
   python3 -m pip install --user virtualenv
   ```
1. Create a new virtual environment within the same directory as the git checkout.
   ```
   cd ScheduleEventHelper
   python3 -m virtualenv --python=python3 seh-env
   ```
1. Activate the new virtual environment
   ```
   source seh-env/bin/activate
   ```
1. Install, into the new virtual environment, the required python modules for this specific environment.  This will be installed within the virtual env which was activated earlier.
   ```
   python3 -m pip install -r requirements.txt
   ```
1. Start Jupyter-lab
   ```
   jupyter-lab
   ```
1. Navigate to the Jupyter notebook checked in here.

# Rules

1. Every team needs a goalkeeper and is placed first.  The number of goal keepers determines the number of teams.
1. All teams have to have the same number of players.  For configurations where this is not possible then no team should have more than 1 member for the smallest team.
1. As much as possible there must be a good distribution of skill across the teams.  This is captured using the skill numeric value (SNV) within the input spreadsheet.  
1. A good distribution of skill does not allow for one team with many highly skilled (3) players and then a few lower skilled (1) players to given it an overall balance.  Many highly skilled players working together are better than average players.
1. Given the overall makeup of a team we next need the right assignment of positions.  If the teams were 8 people then, as an example, we would want: 3 Midfield, 3 Defense, 2 offense.
1. There was a specific request to ensure that Mindy Au be on the team with Maha.

# Team assignments

There are two things that we are trying to balance.  First, each team has to have the same number of people.  
Given certain numbers of players and teams we will, of course, have some teams with one more player than the
minimum.  But we must have the same number of players.  This is paramount.  

Now that the team sizes are the same we want to minimize the difference between the maximum and minimum skill
level across all teams.  

I used the following algorithm.

* For each player to assign to a team:
   * Find all teams with the minimum number of players
   * For each one of these pretend that we were to assign the new player
   * Evaluate the overall min and max total skill level if we made this assignment
   * Choose the best assignment that minimizes the distance between total skill of all teams.

This worked very well in practice.
