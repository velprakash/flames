# flames
Using simple python program to calculate FLAMES 
#sourcecode
def flamescal(n1, n2):
    for i in range(len(n1)):
        for j in range(len(n2)):
            if(n1[i]==n2[j]):
                 n2=n2.replace(n2[j],"*")
                 break
    t=n2.count('*')*2
    #print(t)
    results = ['Friend','Love','Affection','Marriage','Enemy','Sister']
    t=len(n1)+len(n2)-t-1
    i=-1
    while(len(results)>1):      
        count=-1
        while(count<t):
            count=count+1
            i=(i+1)%len(results)            
        results.remove(results[i-1])      
    return results[0]
   
n1 = input('Enter name of first person: ').casefold()
n2 = input('Enter name of second person: ').casefold()
print(n1,' is ', flamescal(n1, n2),' on ',n2)
