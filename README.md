def is_acceptable_password(password: str) -> bool:
    newpassword = set(password)
    if len(newpassword) < 3:
        return False
    password = password.lower()
    if password.find('password') != -1:
        return False
    a = 0
    b = 0
    for i in password:
        if i.isdigit():
            a += 1
        elif i.isalpha():
            b += 1
    if len(password) > 9:
        return True
    if b == 0:
        return False
    if a > 0:
        if len(password) > 6:
            return True
        else:
            return False
    else:
        return False

if __name__ == '__main__':
    print("Example:")
    print(is_acceptable_password('aabaaaabbabbb'))

    # These "asserts" are used for self-checking and not for an auto-testing
    assert is_acceptable_password('short') == False
    assert is_acceptable_password('short54') == True
    assert is_acceptable_password('muchlonger') == True
    assert is_acceptable_password('ashort') == False
    assert is_acceptable_password('muchlonger5') == True
    assert is_acceptable_password('sh5') == False
    assert is_acceptable_password('1234567') == False
    assert is_acceptable_password('12345678910') == True
    assert is_acceptable_password('password12345') == False
    assert is_acceptable_password('PASSWORD12345') == False
    assert is_acceptable_password('pass1234word') == True
    assert is_acceptable_password('aaaaaa1') == False
    assert is_acceptable_password('aaaaaabbbbb') == False
    assert is_acceptable_password('aaaaaabb1') == True
    assert is_acceptable_password('abc1') == False
    assert is_acceptable_password('abbcc12') == True
    print("Coding complete? Click 'Check' to earn cool rewards!")
