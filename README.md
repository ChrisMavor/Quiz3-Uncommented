# Quiz3-Uncommented
Finished code for all 5 questions just not commented on


def dot(vector01,vector02):
  if type(vector01)==list and type(vector02)==list:
    if len(vector01)!=len(vector02):
      return "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
    elif type(vector01[0])==int and type(vector02[0])==int:
      row=0
      for i in range(len(vector01)):
        row+=vector01[i]*vector02[i]
      return "vector01 * vector02 =" , row
    else:
      return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
testv1 = [1,2]
testv2 = [2,2]
print(dot(testv1,testv2))


def vecSubtract(vector01,vector02):
  if type(vector01)==list and type(vector02)==list:
    if len(vector01)!=len(vector02):
      return "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
    elif type(vector01[0])==int and type(vector02[0])==int:
      row=[]
      for i in range(len(vector01)):
        row.append(vector01[i]-vector02[i])
      return "vector01 - vector02 =",row  
    else:
      return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
subtestv1 = [1,2]
subtestv2 = [2,2]
print(vecSubtract(subtestv1,subtestv2))

def scalarVecMulti(scalar,vector):
  if type(scalar)==int and type(vector)==list:
    if type(vector[0])==int:
      row=[]
      for i in range(len(vector)):
        row.append(scalar*vector[i])
      return "scalar * vector =",row  
    else:
      return  "Incorrect sizing. Make sure input 'scalar' is a single integer and input 'vector' is a single list. Make sure inputs are not matrices(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure input 'scalar' is a single integer and input 'vector' is a single list. Make sure inputs are not matrices(list of lists), or strings."
scalarVecTestS = 7
scalarVecTestV = [4,2]
print(scalarVecMulti(scalarVecTestS,scalarVecTestV))

def infNorm(vector):
  if type(vector)==list:
    if type(vector[0])==int:
      square=0
      for i in range(len(vector)):
        square+=vector[i]*vector[i]
      norm=(square)**(1/2)
      return "||vector|| = sqrt(vector[0]^2+vector[1]^2+...+vector[i]^2)=" , norm
    else:
      return  "Incorrect sizing. Make sure input 'vector' is a single list. Make sure input is not a integer, matrix(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure input 'vector' is a single list. Make sure input is not a integer, matrix(list of lists), or strings."
infNormTest = [4,4]
print(infNorm(infNormTest))

def normalize(vector):
  if type(vector)==list:
    if type(vector[0])==int:
      square=0
      for i in range(len(vector)):
        square+=vector[i]*vector[i]
      norm=(square)**(1/2)
      normalized=[]
      for i in range(len(vector)):
        normalized.append(norm*vector[i])
      return "vector*(1/||vector||) =" , normalized 
    else:
      return  "Incorrect sizing. Make sure input 'vector' is a single list. Make sure input is not a integer, matrix(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure input 'vector' is a single list. Make sure input is not a integer, matrix(list of lists), or strings."
normTest = [4,4]
print(normalize(normTest))
