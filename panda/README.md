# Run the command
to run the simulation start it with `python3 -m rl.main`.
Since every time we run the model it takes the same name, it will train it on the same instance, therefore continuing the training from where it stopped last time. To change this and start a new training on a fresh model, we can add the `--suffix` flag and add a string. This will save the model as `rl.111.YOUR_SUFFIX_STRING` in the log/ folder.

## Config
Config contains configuration details about environment, controller and learning algorithms. 

## Controller
Controller contains the joint velocity controller class, actions coming from learning algorithms are interprested as joint velocities but real robot is equipped with torque controller. Controller class converts the joint velocities to joint torques and also performs interpolation between each successive action coming from policy if needed.

## Envionments
Envionments include base enviornment and environments for the Panda Robot and the Grasping task. Panda Robot defines everything robot related. Grasping task defines everything task related including a reward function. Environments also contain an action space class that defines the size and limits of robot's action space to be used in learning

## Models
Models is where everything is actually defined for simulation. Arena, Gripper, Objects and Robot are the classes that use xmls respectively from Assets. Task merges all pieces and instantiates a scene model for MuJoCo to perform the simulation. Task is used later on in the environment.

## RL
RL is where actual learning happens. PPO and SAC are the implemented algorithms. Neural network models are present in policies.


## Utils
Utils contain auxiliaries both for environment defintion and learning part. 

Note: all the files have been commented heavily (with possible output) to have a faster understanding of what's happening.

