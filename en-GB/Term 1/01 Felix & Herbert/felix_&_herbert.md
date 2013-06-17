Level 1

#Felix & Herbert

__Introduction:__



```scratch







```
###Test Your Project






```scratch
	
	When FLAG clicked
	forever
		go to mouse-pointer
		point towards Felix
	(end forever)
```







```scratch
	
	when FLAG clicked
	forever
		point towards mouse-pointer
		move 10 steps
		next costume
		play drum 62 for 0.3 beats
		if touching Herbert
			say Caught you! for 1 secs
		(end if)
	(end forever)
```

###Test Your Project



##STEP 4: Herbert turns into a ghost when he’s caught

__Instead of Felix saying something, we want Herbert to turn into a ghost when he’s caught.__

1. Change Felix’s script to send this message when he catches Herbert.

```scratch
	
	when FLAG clicked
	forever
		point towards mouse-pointer
		move 10 steps
		next costume
		play drum 62 for 0.3 beats
		if touching Herbert
			broadcast caught
			play drum 58 for 0.2 beats
			wait 1 sec
		(end if)
	(end forever)
```

	
	when I receive caught
	switch to costume dead
	wait 0.5 secs
	switch to costume alive
```
	
###Test Your Project






	
	when FLAG clicked
	set score to 0
	forever
		change score by 1
		wait 1 secs
	(end forever)
	
	when I receive caught
	change score by -100
```
	
###Test Your Project


