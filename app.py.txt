import os

def insecure_function(user_input):
    # A common SAST vulnerability: using input directly in an OS command
    os.system("echo " + user_input) # SonarQube should flag this as a command injection vulnerability

user_data = input("Enter something: ")
insecure_function(user_data)