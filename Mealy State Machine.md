A type of [[Finite State Machine]]


- Output depends on both the current state and the current input
- Transition to a new state happens based on input, output is directly generated based on that input and the current state
- Each arc (transition) labeled with an output value
- Output can change immediately when the input changes, even if the state doesn't change - can be a problem when two machines are interconnected
- Tend to have fewer states than [[Moore State Machine]]s

### Diagram:
![[Pasted image 20250120205408.png]]