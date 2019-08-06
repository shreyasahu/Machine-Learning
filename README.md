# Machine-Learning
It contains function for removing duplicate columns

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


ANOTHER WAY

     def dropCol(new_test):
        #new_test=test_data.copy()

    for col in new_test:
        
        if(col in new_test.columns):
            temp=new_test.drop([col],axis=1)        
            for a in temp:            
                if(new_test[col].equals(temp[a])):
                    new_test.drop(a,axis=1,inplace=True)
        
    return new_test        
    dropCol(df)
