- there are three csv files (user, his followers and those people he/she follows)

- there are 5 categories that a user's tweets can be assigned [0, 1, 2, 3, 4]

- the idea is to determine the category a user [user_data.csv] belongs to by analyzing his/her tweets, 
followers tweets [followers.csv] and the tweets of those people he follows [follows.csv]

- if majority of each users tweets [user_data.csv] belongs to a category [i.e 0], AND 
majority of the tweets the users he follows [follows.csv] belongs the same category [i.e 0] OR 
the majority of the tweets of his followers belong to the same category or any other category
then, the category of that user[user-data.csv] is 0.

rules

user-data.csv(max)		followers.csv(max)		follows.csv(max)	category of the user

	0				0				0			0
	0				0				1			0
	0				1				0			0
	0				1				1			1
	0				1				2			0
	0				2				3			0
	0				4				4			4
	1				0				1			1
	1				0				0			0
	1				1				1			1
	1				2				3			1
	1				2				4			1		
	1				4				4			4
	2				4				4			4
	2				2				4			2
	2				3				4			2
	2				1				4			2
	2				4				0			2
	2				2				2			4
	3				3				3			3
	3				2				3			3
	3				1				3			3
	3				0				3			3
	3				0				4			3
	3				4				4			4
	4				1				4			4
	4				0				4			4
	4				4				1			4
	4				2				4			4
e.t.c

after doing the analysis and determing the category of the user, the results of the analysis should be 
generated in the form of a new csv file with the following structure:

user		tweets						category
user_A		tweet_a, tweet_b, tweet_c...			    3
user_B		tweet_a, tweet_b, tweet_c...			    0
.			.					    .
.			.					    .
.			.					    .
user_Z		tweet_a, tweet_b, tweet_c...			    0


that is, one row for each user with all of his/her tweets mapped to the user it belongs too.


the number users, tweets, labels, followers, followee is not fixed (a constant)	

.			 