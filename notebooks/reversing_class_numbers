#change class number 1 to 0 and vice versa (switch crop and weed class) 
import os 
import shutil
%cd /home/jovyan/datasets/all_fields_lincolnbeet/val/labels
files = []
lst_weeds = ['0']
# Add the path of txt folder
for i in os.listdir("/home/jovyan/datasets/all_fields_lincolnbeet/val/labels/"):
    if i.endswith('.txt'):
        files.append(i)

for item in files:
    # define an empty list
    file_data = []

    # open file and read the content in a list
    with open(item, 'r') as myfile:
        for line in myfile:
            # remove linebreak which is the last character of the string
            currentLine = line[:-1]
            data = currentLine.split(" ")
            # add item to the list
            file_data.append(data)
    
    # Increase the first number in any line by one
    for i in file_data:
        if i[0].isdigit():

            if i[0] in lst_weeds:
                temp = 1 
                i[0] = str(int(temp))

            else:
                temp = 0 
                i[0] = str(int(temp))

    # Write back to the file
    f = open(item, 'w')
    for i in file_data:
        res = ""
        for j in i:
            res += j + " "
        f.write(res)
        f.write("\n")
    f.close()
