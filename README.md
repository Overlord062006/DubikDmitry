import csv
with open('space.csv',encoding = 'utf8') as f:
    reader = list(csv.DictReader(f,delimiter = '*', quotechar = '"'))
    for i in range(len(reader)):
        j = i - 1
        key = reader[i]
        while ((float(reader[j]['Name'])) < ((float(key['Name'])))) and (j >= 0):
            reader[j+1] = reader[j]
            j -= 1
        reader[j+1] = key
print('Корабли по номеру')
k = 1
for i in reader:
    if k > 10:
        break
    a = i['Ship']
    b = i['Name']
    print(f"{a}-{b}")
    k += 1
