## Data Directory Structure

```
|data
    |--- sample_submission.csv
    |--- test_input.csv
    |--- test.csv
    |--- train
        |--- input_2023_w[01-18].csv
        |--- output_2023_w[01-18].csv
```
## Variables
### data/train/input_2023_w[01-18].csv
- `game_id:` Game identifier, unique (numeric). 
- `play_id:` Play identifier, not unique across games (numeric)
- `player_to_predict:` whether or not the x/y prediction for this player will be scored (bool)
- `nfl_id:` Player identification number, unique across players (numeric)
- `frame_id:` Frame identifier for each play/type, starting at 1 for each game_id/play_id/file type (input or output) (numeric)
- `play_direction:` Direction that the offense is moving (left or right)
- `absolute_yardline_number:` Distance from end zone for possession team (numeric)
- `player_height:` player height (ft-in)
- `player_weight:` player weight (lbs)
- `player_birth_date:` birth date (yyyy-mm-dd)
- `player_position:` the player's position (the specific role on the field that they typically play)
- `player_side:` team player is on (Offense or Defense)
- `player_role:` role player has on play (Defensive Coverage, Targeted Receiver, Passer or Other Route Runner)
- `x:` Player position along the long axis of the field, generally within 0 - 120 yards. (numeric)
- `y:` Player position along the short axis of the field, generally within 0 - 53.3 yards. (numeric)
- `s:` Speed in yards/second (numeric)
- `a:` Acceleration in yards/second^2 (numeric)
- `o:` orientation of player (deg)
- `dir:` angle of player motion (deg)
- `num_frames_output:` Number of frames to predict in output data for the given game_id/play_id/nfl_id. (numeric)
- `ball_land_x:` Ball landing position position along the long axis of the field, generally within 0 - 120 yards. (numeric)
- `ball_land_y:` Ball landing position along the short axis of the field, generally within 0 - 53.3 yards. (numeric)

### data/train/output_2023_w[01-18].csv
- `game_id:` Game identifier, unique (numeric)
- `play_id:` Play identifier, not unique across games (numeric)
- `nfl_id:` Player identification number, unique across players. (numeric)
- `frame_id:` Frame identifier for each play/type, starting at 1 for each game_id/play_id/ file type (input or output). The maximum value for a given game_id, play_id and nfl_id will be the same as the num_frames_output value from the corresponding input file. (numeric)
- `x:` Player position along the long axis of the field, generally within 0-120 yards. (TARGET TO PREDICT)
- `y:` Player position along the short axis of the field, generally within 0 - 53.3 yards. (TARGET TO PREDICT)