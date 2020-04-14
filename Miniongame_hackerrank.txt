string  = raw_input()
word = list(string)

def occurrences(string, sub):
    count = start = 0
    while True:
        start = string.find(sub, start) + 1
        if start > 0:
            count+=1
        else:
            return count

vow = list('AEIOU')

kv = set()
sc = set()

kwl = set()
swl = set()

swlp = 0
kwlp = 0

for i in word:
    if i in vow:
        kv.add(i)
    else:
        sc.add(i)

for i in xrange(len(word)):
    for j in range(i,len(word)):
        if word[i] in kv:
            kwl.add(string[i:j+1])
#            print '% %',(i,j+1)
        else:
            swl.add(string[i:j+1])
        
#For points

for i in swl:
    swlp = swlp+occurrences(string,i)
    
for i in kwl:
    kwlp = kwlp+occurrences(string,i)
    
if swlp > kwlp:
    print 'Stuart',swlp
elif kwlp > swlp:
    print 'Kevin',kevin
else:
    print 'Draw'