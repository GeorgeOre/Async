# Async
Projects involving the ACT tools developed by Rajit Manohar and his team
We are here in the meeting room

Kwabena made a trip to Sicily and brought back a gift

Reading out Events Hiearchically

Leo is talking out loud with his voice

Animations are included

What does reading out event hiearchically even mean

what is an event?
- Many kinds
- Event cameras and their pixwls are good for this
	You can model the events of a pixel step threshold being passed as an event

Frame cameras are kinda ass!!!!!!
- with event cameras we get 

Row column wise pizel encoding  is king rn. 
 any pixel in a row can make a reow request  for that wentire row
 	Then the entire row gets read out not just the singular pixel that made the original request

You get the entire row dumped into a row latch 
- That gets ruened into groups and that gets serialized
	maybe this means you can parse tis better


There are different important times to pay attention to in oreder to track latency
- Trow : the time it takes for a row to be fetched
- Tgrp : Time for groups to form
	
	Trow should be much longer than Tgrp
		WHYY???


there is a "knee" in the latency vs load (x) graphs


Story time!!!
- Want to go from small unknown group up to the big level league
- The lowest level groups are encoded
	The whole group and all pixels in the group are represented in that encoding
	There is also a "polarity bit" at this lowest level
- There are a bunch of groups that are competing for attention for a node
	Like children fighing for the parents attention
- Node has to order and encode the groups and appends a packet describing what groups are being sent
- Same thing happends with a higher order node that take in lower order nodes until you reach the parent node (TOP)



Leo has done:
- 16 ary tree implementaion with 5 levels
- 1024x1024 pixels
	Competing head to head with industry
- It works and is better
	But the knee still exists wtf???



Math time
	Define
		k :  is the leaves?
		h :  is the height of the tree
		lambda :  is the amount of info loading
		rho :  is the probability of the 1/k of indexes in the thing you are examining

- Probablility
	Row colunm is a two level tree

First we need to understand how to derive Tpacket
Using Tpacket you can take stats to find out what the knee is
	To this day we still do not know what the knee is

	Tpacket is about proportional to k log_k N


he chose alpha equals two
	because it looks nice
		Five looks less nice

What are we trying to optimize for?
- 












