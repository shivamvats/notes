Trivia
======

Sim-time
--------
Set ``use_sim_time`` to true only if there is a clock server publishing the simulated
time. Otherwise, your nodes will keep waiting for the time to be published.
``use_sim_time=True`` typically only when using gazebo or running a ros-bag.

*Note*: ``use_sim_time=true`` can screw up rviz.

TF
==
* Keeps track of the relative transformations between joints.
* There are alternatives as well: KDL.
* RViz needs this to visualize the robot. Hence, even if you are not using TF, make sure it is being published if you need to visualize stuff on RViz.

robot_state_publisher
^^^^^^^^^^^^^^^^^^^^^
This is a ROS package that subscribes to ``/joint_states`` (for joint state) and ``robot_description`` (for the URDF) to commpute its FK (think KDL tree) and publish the transforms via TF (at ``/tf``).

URDF
========
* To check if a urdf file is valid and visualize the link connections (tree),
  run ``check_urdf xyz.urdf``.
* To get a graphical diagram/tree of the robot links run ``urdf_to_graphiz xyz.urdf``
