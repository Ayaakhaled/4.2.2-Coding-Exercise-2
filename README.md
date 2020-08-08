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
