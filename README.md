# godot-behavior-tree
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](http://paypal.me/GabrieleTorini) 

A GDScript implementation of a behavior tree for game AI, based on native Godot nodes and using the built in scene tree editor.

INSTRUCTIONS:
- Copy files in a folder in your project. May have to restart the editor.
- Click the node creation icon. You should see new nodes available. You must use a BehaviourTree as the root node, which should have only a single child. This child can be any of the nodes under the BTNode category, which all inherit from the BTNode class.
- After creating a behavior tree, you must specify who is the owner of the AI (the Agent) and what Blackboard is being used. Blackboards should be created separately and provided with BBServices which act as a kind of 'sensors' to write data on the Blackboard.
- A Behavior Tree flows executing each of its children, which return some kind of success or failure state. Only those branches following a successful node will be executed. 
- The flow of the tree is defined by the so called composite nodes: BTSequence, BTSelector and BTParallel. A sequence is successfull if all the children are successful, while it fails if one of the children fails. The selector is the logical opposite, it succeeds if one children succeeds, and fails if all the children fail. A parallel will run all the children and always succeed regardless. 
- Add BTAction and BTCondition scripts as your leaf nodes, then override them with 'extend script'. Your behaviors and checks will go here.
- BTGuards can be used to temporarily lock branches. Optionally, you can assign an unlocker, which will override the lock time specified. There is also the option to assign a locker. BTGuards can make your behavior very rich and reactive, as well as optimised, as they avoid unnecessary branching and repetition.
- You could have a huge behaviour tree, but the best practice is to follow the component philosophy of Godot and make several smaller behaviour trees for each component of your scene. A behaviour tree can only have one blackboard, but the same blackboard can be used by many trees, so this is particularly handy if you wanna have several trees without also making multiple blackboards.


Tutorials/demos will be included soon. 
If you need support, reach out to me at gabriele.torini@outlook.it or on Discord at kagenashi#8224


If you make amazing AI with the Behavior Tree, consider offerring me a coffee so I can stay awake and improve it :)

[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](http://paypal.me/GabrieleTorini) 
