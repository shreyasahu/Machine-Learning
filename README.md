# Machine-Learning
It contains machine learning codes

FUNCTION FOR REMOVING DUPLICATE COLUMNS


import numpy as np
def dups1(df):
    dupcol = []
    column = df.columns
    df.replace(np.nan,-1,inplace=True)
    for curr_col in range(len(column)-1):
        for sel_col in range(curr_col+1,len(column)):
            if np.array_equal(df[column[curr_col]].values,df[column[sel_col]].values):
             #if test[column[curr_col]].equals(test[column[sel_col]]):
                dupcol.append(column[sel_col])
                #test.drop(test.columns[sel_col],axis=1)
    df.drop(dupcol, axis=1, inplace=True)

    return df
dups1(df)
