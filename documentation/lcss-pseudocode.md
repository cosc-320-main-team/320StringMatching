
``` python
# Non recursive method of lcss
def lcss(x,y):

# Find the length of both strings you are comparing and store them in variables m, n
	m = len(x)
	n = len(y)

# Declare an array to check if solution is already there, if it is we simply return it
# will be used as a double array
table = []

# table[i] and table[i][[j] will contain the length of lcss x[0,...i-1] and y[0...j-1]

    # i = 0... m 
	for i in range(m+1):
        # j = 0... n 
		for j in range(n+1):
			# if letters are not beside each other, add 0 to the table
            if i == 0 or j == 0:
				table[i][j] = 0
			# if letters are beside each other, add to table
            elif x[i-1] == y[j-1]:
				table[i][j] = table[i - 1][j - 1] + 1
			else:
                            table[i][j] = max(table[i-1][j],table[i][j-1])                
            # Table will contain the length of lcss of x and y
            return table[m][n]


```