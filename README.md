def checkio(words: str) -> bool:
    a = 0
    b = 0
    for i in words:
        a += 1
        if i == ' ':
            if words[a - 2].isalpha() and words[a].isalpha():
                b += 1
                if b >= 2:
                    return True
        if i.isdigit():
            words = words[a:]
            a = 0
            b = 0
    if b < 2:
        return False

#These "asserts" using only for self-checking and not necessary for auto-testing
if __name__ == '__main__':
    print('Example:')
    print(checkio("Hello World hello"))
    
    assert checkio("Hello World hello") == True, "Hello"
    assert checkio("He is 123 man") == False, "123 man"
    assert checkio("1 2 3 4") == False, "Digits"
    assert checkio("bla bla bla bla") == True, "Bla Bla"
    assert checkio("Hi") == False, "Hi"
    print("Coding complete? Click 'Check' to review your tests and earn cool rewards!")
