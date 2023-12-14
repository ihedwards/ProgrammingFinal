#stackoverflow.com
#chatgpt.com
#https://stackoverflow.com/questions/64363603/how-to-add-to-i-in-a-range-in-a-for-loop-python
#https://stackoverflow.com/questions/74368204/how-to-pull-specific-data-from-an-array
#https://stackoverflow.com/questions/62893326/calculate-value-in-array-under-certain-condition 
import array

ROWS = 6
COLS = 5


def main():
   results = array.array('d', [0.0] * (ROWS * COLS))
   askUser(results)


def askUser(results):
   currentClasses = []
   i = int(input("\nThis is a final grade calculator, you can put as many classes as you want. How many would you like to input? ")) #ask reader how many classes they want
  
   for _ in range(i):
       #ask for class name, grade, and final
       className_input = input("\nEnter the class name: ")
       finalPercent_input = float(input("Enter the weight of the final (as a decimal): "))
       currentGrade_input = float(input("Enter your current grade (as a whole number): "))
       goalGrade_input = float(input("Enter the grade you want (as a whole number): "))
      
       classInfo = (className_input, finalPercent_input, currentGrade_input, goalGrade_input)
       currentClasses.append(classInfo)
  
   calculator(currentClasses, results)


def calculator(currentClasses, results):
   print("\nCalculated Grades:") 
   for idx, classInfo in enumerate(currentClasses):
       className, finalPercent, currentGrade, goalGrade = classInfo


       calculation = (goalGrade - currentGrade * (1 - finalPercent)) / finalPercent #calculate grades
      
       results[idx] = calculation
  
       print(f"Class: {className}\nGrade Needed: {calculation:.2f}\n") #prints grades
main()
