
# Schedule Event Helper

This is a simple project which made it easy to create the teams for a 100+ person soccer event.

1.  Install necessary prerequisites
   - sudo apt install -y python3
   - python3 -m pip install --user --upgrade pip
   - python3 -m pip install --user virtualenv

1.  Create a new virtual environment within the same directory as the git checkout.
   ```
   cd ScheduleEventHelper
   python3 -m virtualenv --python=python3 seh-env
   ```
1.  Activate the new virtual environment
   ```
   source seh-env/bin/activate
   ```
1.  Install, into the new virtual environment, the required python modules
   ```
   python3 -m pip install -r requirements.txt
   ```
1.  Start Jupyter-lab
   ```
   jupyter-lab
   ```

# Rules

1. Every team needs a goalkeeper and is placed first.  
1. There must be an even distribution of the 'SNV'.  SNV is skilled numeric value.  
1. Given a random distribution of teams we now ensure that we have the right assignment of positions.  If the teams were 8 people then, as an example, we would want: 3 Midfield, 3 Defense, 2 offense.
1. There was a specific request to ensure that Mindy Au be on the team with Maha.


