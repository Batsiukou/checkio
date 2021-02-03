def checkio(number: int) -> int:
    a = 1
    number = str(number)
    for i in number:
        i = int(i)
        if i != 0:
            a = a * i
        else:
            continue
    return a


if __name__ == '__main__':
    print('Example:')
    print(checkio(999))
    
checkio(123405) == 120
checkio(999) == 729
checkio(1000) == 1
checkio(1111) == 1
