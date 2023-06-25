#count number of annotations in label files
import os 
import shutil
%cd /home/jovyan/datasets/grapes_split/val/labels
files = []
annotation_weed = 0
annotation_crop = 0
# counts=0
lst_weeds = ['0']
for i in os.listdir("/home/jovyan/datasets/grapes_split/train/labels/"):
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

    for i in file_data:
        if i[0].isdigit():
            # print(i[0])
            if i[0] in lst_weeds:
                annotation_weed += 1
            else:
                annotation_crop += 1
# print(counts)
print( 'number of weed annotations is', annotation_weed)
print( 'number of crop annotations is', annotation_crop)
