def is_acceptable_password(password: str) -> bool:
    a = 0
    b = 0
    for i in password:
        if i.isdigit():
            a += 1
        elif i.isalpha():
            b += 1
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
    print(is_acceptable_password('shortjjj7'))

    # These "asserts" are used for self-checking and not for an auto-testing
    assert is_acceptable_password('short') == False
    assert is_acceptable_password('muchlonger') == False
    assert is_acceptable_password('ashort') == False
    assert is_acceptable_password('muchlonger5') == True
    assert is_acceptable_password('sh5') == False
    print("Coding complete? Click 'Check' to earn cool rewards!")
