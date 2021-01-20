def is_isogram(string):
    a = string.lower()
    b = 0
    for i in string:
        b += 1
        if i.lower() in a[b:]:
            return False
        string = string[b:]
    return True

if __name__ == '__main__':
    print(is_isogram('MoOse'))
