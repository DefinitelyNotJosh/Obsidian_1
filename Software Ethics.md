Bugs can be deadly - Therac 25, for example

Telephone network outage in the US for ~8 hours in 1991

1. Describe the incident in your own words. What went wrong and what was the impact on the human lives?
DSC put out a patch on their cell towers that caused 3 binary digits of data to be off. The error caused the systems to flood themselves with nonsense messages that rendered the telephone network useless. It's not an exaggeration to say that some people may have died due to the error. Some people weren't able to make 911 calls, some weren't able to call family members who were ill, some important facilities weren't able to contact each other with relevant information. 

2. What was the reason given by the DSC Communications Corporation for not performing normal testing? What motivated them to skip testing in your opinion?
DSC did not do proper testing because they were convinced that the change was too small to warrant the long testing process they normally do. In their own words, testing normally would take around 4 months, and that would cost the company money and resources that they would be able to spend elsewhere


As a developer at DSC - 
- lesson learned
Run tests, understand the code base a little better before making alterations
- Responsibility
Don't carry any responsibility in this - expecting us to understand millions of commands perfectly and voicing that concern to upper management is unreasonable - nobody expected the error to occur. We did our jobs, management didn't want to expend the resources that would be called for during testing. We would've done the tests gladly.
- Actions
Could be more vocal about running unit tests, but respect toward company leadership should be considered
- Ethics
Yes we made a mistake, but hindsight is 20/20, obviously if we knew this was the effect we would've been more careful and not have introduced the bug, but you can't put this on us. Imagine this: You leave your car accidentally unlocked while leaving to work. Later in the day, a carjacker takes your car and ends up hitting and killing a pedestrian. Are you to blame for the death because you kept your car unlocked? No, of course not. Yes, you unknowingly contributed to the decision, but you are not in any way shape or form legally responsible
- Impacts



