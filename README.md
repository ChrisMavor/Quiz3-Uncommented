def dot(vector01,vector02):
  """
  Inputs:
    vector01: vector in format of a list.
    vector02: vector in format of a list.
  Output:
    dot:
  This function 'dot' takes inputs in the format of lists, or vectors, and performs the dot product of the vectors. Dot product refers to the itemized multiplication of corresponding elements in each vector and sums the product of the itemized multiplication. 
  If there is a mistake in the formating, an error will result specifying the inputs to change in format type so that the function can opperate properly. 
  If proper inputs are given, the end result will return a integer called 'row'.
  """
  if type(vector01)==list and type(vector02)==list:
    #This if statement checks the input type to make sure that they are both lists (or vectors).
    if len(vector01)!=len(vector02):
      #if the first condition was passed, then they must also be the same length so that proper dot products can be multiplied and not run into a index issue. In this loop, there is a return for an inpropper length and sizing or type.
      return "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
    elif type(vector01[0])==int and type(vector02[0])==int:
      #If the lengths of the vectors are the same lengths then in this loop they will be indexed based on the range.
      dot=0 #this sets up an empty integer for the sum of the products.
      for i in range(len(vector01)):
        dot+=vector01[i]*vector02[i]
        #dot is an empty vector. the for loop is indexing 
      return 'vector01 * vector02 =' , dot
      #answer for proper input values.
    else:
      return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
#################
#Test Conditions#
#################
testv1 = [1,2,3]
testv2 = [2,2,2]
#testv1 = 1
#testv2 = 4
#testv1 = [2,3,4]
#testv2 = 'a'
print("Problem 1:",dot(testv1,testv2))


def vecSubtract(vector01,vector02):
  """
  Inputs:
    vector01:
    vector02:
  Output:
    row: itemized vector subtraction indexing each element respective to each vector.

  Function vecSubtraction is taking two vectors and subtracting vector02 from vector02. A vector is the result meaning a list of itemized subtracted elements are the answers. 
  """
  if type(vector01)==list and type(vector02)==list:
    if len(vector01)!=len(vector02):
      #This ensures that the lengths are similar so that subtraction is valid and there isnt an indexing error.
      return "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
    elif type(vector01[0])==int and type(vector02[0])==int:
      row=[]#defining an empty list to store the itemized subtraction into a new list that resutls the subtraction.
      for i in range(len(vector01)):
        row.append(vector01[i]-vector02[i])
        #for each i there is an itemization of the vector inputs to subtract the elements from each vector and storing it into a list 'row'.
      return "vector01 - vector02 =",row  
      #proper result from proper inputs.
    else:
      return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure both inputs are a single list of the same length. Make sure inputs are not integers, matrices(list of lists), or strings."
#################
#Test Conditions#
#################

subtestv1 = [1,2]
subtestv2 = [2,2]
#subtestv1 = 1
#subtestv2 = 4
#subtestv1 = [2,3,4]
#subtestv2 = 'a'
print("Problem 2:",vecSubtract(subtestv1,subtestv2))

def scalarVecMulti(scalar,vector):
  """
  Inputs:
    Scalar: an integer input
    Vector: a list of integer values
  Outputs:
    row: scalar vector multiplication where the scalar multiplies by each element in the vetor and returns a list or vector.

  """
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
#################
#Test Conditions#
#################
scalarVecTestS = 7
scalarVecTestV = [4,2]
#scalarVecTestv1 = 1
#scalarVecTestv2 = 4
#scalarVecTestv1 = [2,3,4]
#scalarVecTestv2 = 'a'
print("Problem 3:",scalarVecMulti(scalarVecTestS,scalarVecTestV))

def infNorm(vector):
  if type(vector)==list:
    if type(vector[0])==int:
      #infNorm
      absvector=[]
      for i in range(len(vector)):
        absvector.append(abs(vector[i]))

      currentMax=absvector[0]

      for i in range(len(vector)):
        if currentMax>=absvector[i]:
          currentMax=currentMax
        else:
          currentMax=absvector[i]
          

      return currentMax
    else:
      return  "Incorrect sizing. Make sure input 'vector' is a single list. Make sure input is not a integer, matrix(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure input 'vector' is a single list. Make sure input is not a integer, matrix(list of lists), or strings."
#################
#Test Conditions#
#################
infNormTest = [60,153,59]
#infNormTest = 1
#infNormTest = [4]
#infNormTest = [2,3,4]
#infNormTest = 'a'
print("Problem 4:",infNorm(infNormTest))

def normalize(vector):
  if type(vector)==list:
    if type(vector[0])==int:
      
      currentMax=infNorm(vector)    
      normalized=[]    
      for i in range(len(vector)):
        normalized.append((1/currentMax)*vector[i])
      return "vector*(1/infNorm(vector)) =" , normalized 
    else:
      return  "Incorrect sizing. Make sure input 'vector' is a single list. Make sure input is not a integer, matrix(list of lists), or strings."
  else:
    return  "Incorrect sizing. Make sure input 'vector' is a single list. Make sure input is not a integer, matrix(list of lists), or strings."
#################
#Test Conditions#
#################
normTest = [43,4]
#normTest = 1
#normTest = 'a'
#normTest = [2,3,4]
#normTest = [[2],[3],[4]]
print("Problem 5:",normalize(normTest))
