# 🛡️the password checker
# Author: hajar1010
# Description:A simple Python script that checks the strength of a password based on length, digits, symbols, and letter case.
import re

# ask the user to enter their name
pword = input("enter your password !!")


# check the digits and symbols
def checker():
    has_digit = False
    has_symbol = False
    for i in pword:
        if i.isdigit():
            has_digit = True
        if not i.isalnum():
            has_symbol = True
    return has_digit, has_symbol


# check  the cases
def cases():
    has_lower = False
    has_upper = False
    for i in pword:
        if i.islower():
            has_lower = True
        if i.isupper():
            has_upper = True
    return has_lower, has_upper


# check the length
def lenght():
    len_wanted = False
    if len(pword) < 8:
        return len_wanted
    else:
        return not len_wanted


# capturing the results
has_digit, has_symbol = checker()
has_lower, has_upper = cases()
len_wanted = lenght()
# rating the password
score = 0
if has_digit:
    score += 1
if has_symbol:
    score += 1
if has_lower:
    score += 1
if has_upper:
    score += 1
if len_wanted:
    score += 1

if score <= 2:
    print(" Weak password")
elif score == 3 or score == 4:
    print("Medium password")
else:
    print("Strong password")

