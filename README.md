# GladBehavior.Tree

Supports netstandard1.0 and net40!

GladBehavior.Tree is a [Behavior Tree (BT)](https://en.wikipedia.org/wiki/Behavior_tree_(artificial_intelligence,_robotics_and_control)) implementation that supports generic contexts/agents. There are many differing implementations of behavior trees but GladBehavior.Tree attempts to adhere to the common implementation found in many other popular libraries. Behavior Trees allow for modular and reusable construction of AI models. With the custom nodes being the reusable components that compose a Behavior Tree.

## Node Types

### Selector

The [selector node in GladBehavior.Tree](https://github.com/HelloKitty/GladBehavior.Tree/blob/master/src/GladBehaviour.Tree/Nodes/Composite/SelectorTreeNode.cs) is the OR of the nodes meaning that evaluation of composed nodes is short-circuited. This means nodes are evaluated until a Success, Running state, or all of them fail. This node re-enters Running nodes during subsequent node evaluation.

### Sequence

The [sequence node in GladBehavior.Tree](https://github.com/HelloKitty/GladBehavior.Tree/blob/master/src/GladBehaviour.Tree/Nodes/Composite/SequenceTreeNode.cs) is the AND of the nodes meaning that evaluation of composed nodes succeeds only if all nodes succeed. This means nodes are evaluated until all are Success, a Running state is encountered, or one of them fails. This node re-enters Running nodes during subsequent node evaluation.

### Inverter

The [inverter node in GladBehavior.Tree](https://github.com/HelloKitty/GladBehavior.Tree/blob/master/src/GladBehaviour.Tree/Nodes/Decorator/InverterTreeNode.cs) is a decorator that decorates a node, which can be considered a child node, and inverts the resulting evaluated state. Success is transformed to Failure and vice-versa. Running state is left unchanged.

### Condition

The [condition node in GladBehavior.Tree](https://github.com/HelloKitty/GladBehavior.Tree/blob/master/src/GladBehaviour.Tree/Nodes/Leafs/ConditionTreeNode.cs) is a leaf that provides a simplified binary API for evaluating a condition. A condition is either true of false meaning Success and Failure respectively. A condition node can never be in a Running state.

### PrioritySelector

The [priority selector node in GladBehavior.Tree](https://github.com/HelloKitty/GladBehavior.Tree/blob/master/src/GladBehaviour.Tree/Nodes/Composite/PrioritySelectorTreeNode.cs) is exaclty like the Selector node however it emphasizes priority nodes, nodes first in the child composite collection, by re-running from the begining every evaluation regardless of a potentially running node.

### PrioritySequence

The [priority sequence node in GladBehavior.Tree](https://github.com/HelloKitty/GladBehavior.Tree/blob/master/src/GladBehaviour.Tree/Nodes/Composite/PrioritySequenceTreeNode.cs) is exaclty like the Sequence node however it emphasizes priority nodes, nodes first in the child composite collection, by re-running from the begining every evaluation regardless of a potentially running node.

## Tests

TODO

## Builds

**NuGet:** https://www.nuget.org/packages/GladBehaviour.Tree

**MyGet:** [![hellokitty MyGet Build Status](https://www.myget.org/BuildSource/Badge/hellokitty?identifier=21927a8e-4d7e-4f19-b509-ec35f9ea739f)](https://www.myget.org/)

## License

MIT
