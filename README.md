# Python-for-Data-Analysis
import pandas as pd
import numpy as np
df = pd.read_csv("C:\\Users\\ccamiolo\\Documents\\Full_Data_1900_1940\\NewData.csv")
pd.set_option('chained_assignment', None)

df["Types of Materials"]= ""
df["DESCRIPTION, COMMENTS"]= df["DESCRIPTION, COMMENTS"].astype(str)
df["DESCRIPTION, COMMENTS"]= df["DESCRIPTION, COMMENTS"].map(str.upper)
b_type=[]
for i in range(0, len(df)):
    comments = df["DESCRIPTION, COMMENTS"][i]
    if (len(comments)>0):
        if ('BRK' in comments or 'BRICK'  in comments or 'BK'  in comments):
            df["Types of Materials"][i] = 'BRICK '
       
        if ('STONE' in comments ):
            df["Types of Materials"][i] = df["Types of Materials"][i]+'STONE '

        if ('CONCRETE' in comments):
            df["Types of Materials"][i] = df["Types of Materials"][i]+'CONCRETE '

        if ('TERRA COTTA' in comments):
            df["Types of Materials"][i] = df["Types of Materials"][i]+'TERRA COTTA '

        if ('STEEL' in comments):
            df["Types of Materials"][i] = df["Types of Materials"][i]+'STEEL '

        if ('GRANITE' in comments):
            df["Types of Materials"][i] = df["Types of Materials"][i]+'GRANITE '
            
        if ('METAL' in comments):
            df["Types of Materials"][i] = df["Types of Materials"][i]+'METAL '

        if ('IRON' in comments):
            df["Types of Materials"][i] = df["Types of Materials"][i]+'IRON '

        if ('CEMENT' in comments):
            df["Types of Materials"][i] = df["Types of Materials"][i]+'CEMENT '
            
        if ('GLASS' in comments):
            df["Types of Materials"][i] = df["Types of Materials"][i]+'GLASS '

df
    
df.to_csv('C:\Users\ccamiolo\Documents\Full_Data_1900_1940\Materials.csv')
