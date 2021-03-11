 ```python
    
    KMP Search Function:
        input variables:
            pattern : String
            textToSearch : String
        define M = length(pattern), define N = length(textToSearch)
        define lpsArray of M length
        define j = 0, define i = 0  #iterator for pattern and textToSearch
        Compute Longest Prefix Suffix with input variables: pattern, M, lpsArray
        while i < N:
            if pattern[j] == textToSearch[i]:
                j++
                i++
            if j == M:
                #Log that we found a pattern here 
                j = lpsArray[j - 1]
            else if i < N and pattern[j] != textToSearch[i]:
                #lpsArray[0 .. lpsArray[j - 1]] characters will match here anyways 
                if j != 0:
                    j = lpsArray[j - 1]
                else:
                    i++ 

    Computing the Longest Prefix Suffix:
        input variables: 
            pattern : String 
            patternLength : Number
            lpsArray : Array
        define lenPPS = 0 #length of the previous prefix suffix
        set lpsArray[0] = 0
        define i = 1 #iterator
        #Calculates lpsArray[1 to M-1]
        while i < patternLength:
            if pattern[i] == pattern[lenPPS]:
                lenPPS++
                lpsArray[i] = lenPPS
                i++
            else:
                if lenPPS != 0:
                    lenPPS = lpsArray[lenPPS - 1]
            else:
                lpsArray[i] = 0
                i++
