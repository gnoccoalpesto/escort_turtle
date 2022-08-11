# escort_turtle

[escort mission](https://www.youtube.com/watch?v=Glxn4xtegpg) played by 2 teams of turtlebots

DT (DEFENDING TEAM): must escort the TOI (turtle of interest) to the TP(target point), avoiding that the attackers "harm" the TOI

AT (ATTACKING TEAM): must prevent TOI to reach the TP harming it 

note: teams' components are called XT_i

HARM MECHANISM: by staying "close enough" to the TOI for "enough time", attackers will kill it

DEFENSE MECHANISM: the defenders can act by pushing back "far enough" the attackers from TOI

TOI: will plan a path to the TP (map/obstacles is known)... (what about spicying things up with little randomness)

ENVIRONMENT: as for beginning, big room, with obstacles; already mapped
                divided in square tiles

SP (START POINT): (as for the beginning) fixed

TP: same as SP


RL BASED BEHAVIOUR:

TOI: fixed behaviour; uses a well established planner within ROS

DT and AT should learn their strategies

each team acts for maximizing its own, teamwise, reward

## REWARDS 
as for now, no reward based on distance(TOI,TP) is given

rewards are shared by each member of the team (cooperation) and different between teams (competition)

DT: positive:
     proportional to TOI's health
     + proportional to distance (AT_i,TOI)

    negative reward:
        each time AT_i hurts TOI


AT: negative reward:
        proportional to TOI's health