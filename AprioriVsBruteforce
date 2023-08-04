import time from itertools 
import combinations
minimum_support = int(input("Enter here the min support- ")) minimum_confidence = int(input("Enter here the min confidence- ")) begin = time.time()
file_open = open("DS_1.txt", "r") f_of_data = file_open.readlines() listOfItems = []
list_items = 0 all_items={} a= {}
i_list = []
print("input-transactions-") print()

for l in f_of_data:
l = l.replace("\n", "") print(l)
listOfItems.append("".join(l.split(" ")[1].split(","))) b=set()
for x in "".join(l.split(" ")[1:]).split(","):

if (x,) in a:
a[(x,)] += 1
else:
a[(x,)] = 1
b.add(x) i_list.append(b) list_items+=1

f_set = {} e_set = [] print()
print("Item Sets of size", 1) print()
for x in a:
 
print(x,round(a[x]*100/list_items))
if (a[x]/20)*100 >= minimum_support: f_set[x] = a[x]
else:
e_set.append(set(x)) all_items.update(a)
l = []
for x in f_set.keys(): l.append(x[0])


def find_frequent_Sets(l, elims, i_list, n): combos = combinations(l, n)
s_c_dict = {} for x in combos:
set_of_x = set(x)
x = tuple(sorted(x)) for j in i_list:
if set_of_x.issubset(j): if len(elims) > 0:
c = 0
for k in elims:
if k.issubset(set_of_x): c = 1
break if not c:
if x in s_c_dict: s_c_dict[x] += 1
else:
s_c_dict[x] = 1
else:
if x in s_c_dict: s_c_dict[x] += 1
else:
s_c_dict[x] = 1 f_set_final = {} elim_set_final = []
 
if len(s_c_dict) > 0:
print("Size of Item_sets: ", n) print()
for x in s_c_dict: print(x,round(s_c_dict[x]*100/list_items,2))
if (s_c_dict[x]/list_items)*100 >= minimum_support: f_set_final[x] = s_c_dict[x]
else:
elim_set_final.append(set(list(x))) print()
if len(f_set_final) > 0: all_items.update(s_c_dict) Assoc_rules(f_set_final)
return f_set_final, elim_set_final return None,None

def Print_items(f_set,n):
print("Itemsets post iteration of size: ", n) print("Itemset", "Support value")
print()
for x in f_set: print(x,round(f_set[x]*100/list_items,2),)
print()

def Assoc_rules(f_set): for item in f_set.keys():
print("A_Rule for the itemset - ",item) print("Support","Confidence") SizeOfSet=len(item) itemset=set(item)
while SizeOfSet-1>0:
combos = combinations(item, SizeOfSet-1) for x in combos:
left_items=x right_items=tuple(itemset-set(x))
item_confidence=round(all_items[item]*100/ all_items[left_items],2)
if item_confidence>=minimum_confidence:


 
                 print(left_items,"->",right_items,item_confidence,"Qualified")
                 else:
                 print(left_items,"-->",right_items,item_confidence,"Unqualified")

                 SizeOfSet -=1
                 print()
                 print()
                item_set_size = 1
                while len(l) > item_set_size:
                f_set1, e_set1 = find_frequent_Sets(l, e_set, i_list, item_set_size + 1)
                if not f_set1:
                break 
                listOfItems = []
               for items in list(f_set1.keys()):
               for x in items:
               listOfItems.append(x) l = list(set(listOfItems))
               e_set = e_set1 f_set=f_set1
               item_set_size += 1
               print('The Apriori algorithm is executed with the time of : %s ' % (time.time()
- begin), "seconds")
