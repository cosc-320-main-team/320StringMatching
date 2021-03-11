```python
define d = 256 #Number of characters in input alphabet
Search Function:
    input variables:
        pattern : String
        textToSearch : String
        q : Prime Number
    M = length(pattern), N = length(textToSearch)
    define i, j, p, t, = 0
    define h = 1

    #pow(d, M-1) % q
    for i = 0; i < M-1; i++:
        h = (h * d) % q

    #Calculates hash values for pattern and first M characters 
    for i = 0; i < M; i++:
        p = (d * P + pattern[i]) % q
        t = (d * P + textToSearch[i]) % q

    #Loop through the pattern and increase the starting index by 1
    for i = 0; i <= N - M; i++:
        #Check hash values of current window and pattern
        if p == t:
            #Check each character
            for j = 0; j < M; j++:
                if textToSearch[i + j] != pattern[j]:
                    break
            if j == M:
                #Log pattern found at i
        #Calculate the hash for the next window to compare
        if i < N - M:
            t = (d * (t - textToSearch[i] * h) + textToSearch[i + M])) % q

        # if t is a negative value, convert it to a positive one
        if t < 0:
                t = t + q
