import math
import sys

def calc(grid):
    row_len = len(grid) 
    col_len = len(grid[0])
    p=0
    
    for i in range(row_len):
        for j in range(col_len):
            if(grid[i][j]=='C'):
                grid[i][j]=1
            else:
                grid[i][j]=0
      
    cache = [[0 for k in range(col_len)] for l in range(row_len)] 
      
    for i in range(0, row_len):  
        for j in range(0, col_len): 
            if (grid[i][j] == 1): 
                # if row(i) or column(j) is 0, set to 1 or 
                if i == 0 or j == 0: 
                    cache[i][j] = min(grid[i][j], 1) 
                else: 
                    cache[i][j] = min(cache[i][j-1], cache[i-1][j],cache[i-1][j-1]) + 1
            else: 
                cache[i][j] = 0
      
    max_in_cache = cache[0][0]  
    max_i = 0
    max_j = 0
      
    for i in range(row_len):  
        for j in range(col_len):  
            if max_in_cache < cache[i][j]:  
                max_in_cache = cache[i][j]  
                max_i = i  
                max_j = j  
                #print("max_i"+str(max_i))
                #print(max_in_cache)
    for i in range(max_i, max_i - max_in_cache, - 1):  
        p=p+1
    #print("p"+str(p))
    return p

z=[]
N=int(input())
if(N==2):
    count,c2=0,0
    for i in range(N):
        c2=c2+list(map(str,input().split())).count('D')
    if(c2==0):
        sys.stdout.write(str(0))
        sys.stdout.flush()
    if(c2==4):
        sys.stdout.write(str(2))
        sys.stdout.flush()
    if(c2>0 and c2<4):
        sys.stdout.write(str(1))
        sys.stdout.flush()
if(N>2 and N<100):
    count,c2=0,0
    for i in range(N):
        m=list(map(str,input().split()))
        z.append(m)
        c2=c2+m.count('D')
    count=math.sqrt(c2)
    if(count>=0 and count<=N):
        if(math.floor(math.sqrt(c2))+0.5<count):
            sys.stdout.write(str(math.floor(count)))
            sys.stdout.flush()
        else:
            t=calc(z)
            print("T"+str(t))
            if(math.floor(count)-1==t):
                sys.stdout.write(str(math.floor(count)-1))
                sys.stdout.flush()
            else:
                sys.stdout.write(str(math.floor(count)))
                sys.stdout.flush()