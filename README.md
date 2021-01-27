def split_pairs(a):
    b = ''
    c = 0
    e = []
    if len(a) == 0:
        e = a
    elif len(a) % 2 == 0:
        for i in a:
            c += 1
            b = b + i
            if len(b) == 2:
                a = a[c:]
                b = b.split()
                e = e + b
                c = 0
                b = ''
    elif len(a) % 2 != 0:
        a = a + '_'
        for i in a:
            c += 1
            b = b + i
            if len(b) == 2:
                a = a[c:]
                b = b.split()
                e = e + b
                c = 0
                b = ''
    return e   


if __name__ == '__main__':
    print("Example:")
    print(list(split_pairs('abcdf')))

    # These "asserts" are used for self-checking and not for an auto-testing
    assert list(split_pairs('abcd')) == ['ab', 'cd']
    assert list(split_pairs('abc')) == ['ab', 'c_']
    assert list(split_pairs('abcdf')) == ['ab', 'cd', 'f_']
    assert list(split_pairs('a')) == ['a_']
    assert list(split_pairs('')) == []
    print("Coding complete? Click 'Check' to earn cool rewards!")
