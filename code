class Email:
    specialchar = [' ', '_', '.', '-']
    char = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', \
            'u', 'v', 'w', 'x', 'y', 'z', '0', '1', '2', '3', '4', '5', '6', '7', '8', '9', '-', '.']

    def __init__(self, email: str):
        self.email = email
        self.emailParts = self.email.split('@')

    def allowedChar(self, mailpart: str): #should be (a-z), (0-9), ('.', '_')
        for i in mailpart:
            if i not in Email.char:
                return False
        return True

    def moreChar(self, mailpart: str): #should be ('.', ' ', '-', '_')
        for i in mailpart:
            if i not in Email.specialchar and not(i.isalnum()):
                return False
        return True

    def BeginEnd(self, mailpart: str): #should not be any special character at beginnig or end
        return mailpart[0] not in Email.specialchar and mailpart[-1] not in Email.specialchar

    def twodots(self, mailpart: str): #should not be two consecutive dots
        dot_list = mailpart.split('..')
        if len(dot_list) == 1:
            return True
        return False

    def checkdomain(self, mailpart: str): #last portion of domain must contain atleast two characters
        domain_list = mailpart.split('.')
        if len(domain_list) > 1:
            return False if len(domain_list[-1]) == 1 else True
        return False

    def checkPersonInfo(self):
        return self.allowedChar(self.emailParts[0]) and self.moreChar(self.emailParts[0]) and self.BeginEnd(self.emailParts[0]) and self.twodots(self.emailParts[0])

    def checkDomainInfo(self):
        return self.allowedChar(self.emailParts[-1]) and self.checkdomain(self.emailParts[-1]) and self.BeginEnd(self.emailParts[-1]) and self.twodots(self.emailParts[-1])

    def isValid(self):
        if self.checkPersonInfo() and self.checkDomainInfo():
            print("Entered Email is valid")
        else:
            print("Entered Email is invalid")


email = input("Enter the Email you want to check: \n")
email1 = Email(email)
email1.isValid()
# print(email1.checkDomainInfo())
# print(email1.checkPersonInfo())
# print(f"{email1.allowedChar(email1.emailParts[0])}, {email1.moreChar(email1.emailParts[0])}, {email1.BeginEnd(email1.emailParts[0])}, {email1.twodots(email1.emailParts[0])}")
