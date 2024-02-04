INTERACTIONs DATASET FILE DESCRIPTION
------------------------------------------------------------------------------------
------------------------------------------------------------------------------------
The file criteo.inter consists of a portion of Criteo's trafic over a period of several days.
Each record/line in the file has the following fields: label, I1-I13, C1-C26

- **index** - Index of the data and its type is float.
- **Label** - Target variable that indicates if an ad was clicked (1) or not (0). Its type is float.
- **I1-I13** - A total of 13 columns of integer features (mostly count features) and its type is float.
- **C1-C26** - A total of 26 columns of categorical features. The values of these features have been hashed onto 32 bits for anonymization purposes. Its type is token. 

