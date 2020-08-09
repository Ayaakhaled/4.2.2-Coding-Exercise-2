# 4.2.2-Coding-Exercise-2
GTx: CS1301xIII Computing in Python III: Data Structures , Lesson 2: Declaring Strings in Python| 

1)4.2.3 Coding Exercise 2

#Write a function called "last_n" that accepts two arguments:
#a string search_string and an integer n. The function should
#return the last n characters from search_string. If
#search_string is shorter than n characters, then it should
#return the entire value of search_string.


#Write your function here!
def last_n(search_string,n):
  if len(search_string) < n:
        return search_string
  else:
    return search_string[-n:]


#The code below will test your function. If your function
#works correctly, this should print 789, saur, and 1.
print(last_n("123456789", 3))
print(last_n("Bulbasaur", 4))
print(last_n("1", 5))



2)) 4.2.4 Coding Exercise 1
#Write a function called fancy_find. fancy_find should have
#two parameters: search_within and search_for.
#
#fancy_find should check if search_for is found within the
#string search_within. If it is, it should print the message
#"[search_for] found at index [index]!", with [search_for]
#and [index] replaced by the value of search_for and the
#index at which it is found. If search_for is not found
#within search_within, it should print, "[search_for] was
#not found within [search_within]!", again with the values
#of search_for and search_within.
#
#For example:
#
#  fancy_find("ABCDEF", "DEF") -> "DEF found at index 3!"
#  fancy_find("ABCDEF", "GHI") -> "GHI was not found within ABCDEF!"


#Add your function here!
def fancy_find(search_within,search_for):
    if search_for in search_within:
        return search_for+" found at index "+str(search_within.find(search_for))+"!"
    elif search_for not in search_within:
        return search_for+" was not found within "+search_within+"!"
print(fancy_find("ABCDEF", "DEF"))
print(fancy_find("ABCDEF", "GHI"))








3) 4.2.5 Coding Exercise 1
#Write a function called "num_words" that accepts a string 
#as an argument and returns the number of words in the 
#string. You can assume all words are separated by a space,
#and that the string has at least one word. You do not need
#to worry about punctuation.
#
#For example:
#
#  num_words("Veni, Vidi, Vici.") -> 3
#
#This time, you may not use any loops. Hint: split() might
#come in handy.

def num_words(str1):
  res = len(str1.split())
  return res
print(num_words("Vini, Vidi, Vici."))
print(num_words("Hello, world!"))
print(num_words("HeyDavidwhyaren'ttherespacesinthissentence"))


4) Coding Problem 4.2.4
#Write a function called "in_parentheses" that accepts a 
#single argument, a string representing a sentence that
#contains some words in parentheses. Your function should
#return the contents of the parentheses.
#
#For example:
#
# in_parentheses("This is a sentence (words!)") -> "words!"
#
#If no text appears in parentheses, return an empty string.
#Note that there are several edge cases introduced by this:
#all of the following function calls would return an empty
#string:
#
# in_parentheses("No parentheses")
# in_parentheses("Open ( only")
# in_parentheses("Closed ) only")
# in_parentheses("Closed ) before ( open")
#
#You may assume, however, that there will not be multiple
#open or closed parentheses.


#Write your function here!
import re

def in_parentheses(a_string):

   regeX = re.compile(".*?\((.*?)\)")

   result1 = re.findall(regeX, a_string)
   result2 = str(result1).replace("[","")
   result3 = str(result2).replace("]","")
   result = result3.strip("'")

   return(result)

print(in_parentheses("This is a sentence (words!)."))
print(in_parentheses("No parentheses here!"))
print(in_parentheses("David tends to use parentheses a lot (as he is doing right now). It tends to be quite annoying."))
print(in_parentheses("Open ( only"))
print(in_parentheses("Closed ) only"))
print(in_parentheses("Closed ) before ( open"))
print(in_parentheses("That's a lot of test cases(!)"))








Coding Problem 4.2.8 

#Write a function called string_finder. string_finder should
#take two parameters: a target string and a search string.
#The function will look for the search string within the
#target string.
#
#The function should return a string representing where in
#the target string the search string was found:
#
# - If search string is at the very beginning of target
#   string, then return "Beginning". For example:
#   string_finder("Georgia Tech", "Georgia") -> "Beginning"
#
# - If search string is at the very end of target string,
#   then return "End". For example:
#   string_finder("Georgia Tech", "Tech") -> "End"
#
# - If search string is in target string but not at the
#   very beginning or very end, then return "Middle. For
#   example:
#   string_finder("Georgia Tech", "gia") -> "Middle"
#
# - If search string is not in target string at all, then
#   return "Not found". For example:
#   string_finder("Georgia Tech", "Idaho") -> "Not found"
#
#Assume that we're only interested in the first instance
#of the search string if it appears multiple times in the
#target string, and that search string is definitely
#shorter than target string.
#
#Hint: Don't be surprised if you find that the "End" case
#is the toughest! You'll need to look at the lengths of
#both the target string and the search string.


#Write your function here!
def string_finder(target_string,search_string):
    if search_string not in target_string : 
        return "Not found"
    if target_string.startswith(search_string):
        return "Beginning"
    elif target_string.endswith(search_string):
        return "End"
    elif target_string.find(search_string) != -1:
        return "Middle"
   

#Below are some lines of code that will test your function.
#You can change the value of the variable(s) to test your
#function with different inputs.
#
#If your function works correctly, this will originally
#print: Beginning, Middle, End, Not found, each on their own
#line.
print(string_finder("Georgia Tech", "Georgia"))
print(string_finder("Georgia Tech", "gia"))
print(string_finder("Georgia Tech", "Tech"))
print(string_finder("Georgia Tech", "Idaho"))
