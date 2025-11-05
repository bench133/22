# 22
code6
f = open('273A.txt')
m = []
claster = [[] for i in range(3)]
for s in f:
    x,y = [float(c) for c in s.split()]
    m.append([x,y])
    if -1 <= x <=2 and 6<= y <=9:
        claster[0].append ([x,y])
    if 0 <= x <= 3 and 3<= y <=6:
        claster[1].append ([x,y])
    if -1.5 <= x <= 0.5 and -1<= y <=2:
        claster[2].append ([x,y])
      
def centroid(claster):
    maxi = 10**10
    maxix, maxiy = 0,0
    for x1,y1 in claster:
        d = 0
        for x2,y2 in claster:
            d += ((x2-x1)**2 + (y2-y1)**2)** 0.5
        if d < maxi:
            maxi,maxix,maxiy = d, x1, y1
    return maxix, maxiy
 
maxi = max(len(i) for i in claster)
claster = [j for j in claster if len(j)!= maxi]
center = [centroid(n) for n in claster]
sumx, sumy = 0, 0
for x,y in center:
    sumx += x
    sumy += y
otv1, otv2 = int(sumx*10000/len(center)), int(sumy*10000/len(center))    
print(otv1, otv2)
