Must have at least one use case scenario for every functional requirement
- A sequence of steps written in plain English that will lead from initial state to completion of the task
- From perspective of an "actor"- a person/device/program that interacts with the software in some way
- Each scenario answers:
	- Who is the primary actor, secondary actor(s), etc?
	- What are the actors' goals?
	- What pre-conditions should exist before the story starts?
	- What main tasks/functions will be performed by the actor?
	- What extensions might be considered as the story is described?
	- What variations in the actors' interaction are possible?
	- What system information will the actor acquire, produce, or change?
	- Will the actor have to inform the system about changes in the external environment?
	- Does the actor wish to be informed about unexpected changes?


Example
- Use case: "send a gif meme"
- Actor: 18-22 year old student at UP, reasonable technical fluency including browsing
- Pre-conditions: 
	- On a social media platform
	- Has an internet condition
	- Has an email address
	- Both users signed into their e-mail account
	- use gmail server version 1032.123.456

Description: "Happy.path"
1. Find the meme on social media platform
2. Right click (or click with two fingers on laptop)
3. Click "save as" and choose gif format
4. Save to appropriate location in local machine's file system
5. Open emailing client and start email creation
6. Enter correct recipient address
7. Enter subject
8. Attach gif file using email file attachment system
		- locate file on local machine file system
9. Add any relevant info in the body
10. Send email

Alternates:
- Gif is 100gb
- No internet connection
- Email address is invalid
- File format of .gif is not accepted as an attachment
