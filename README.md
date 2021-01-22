def unique_in_order(iterable):
    if len(iterable) == 0:
        return []
    a = 0
    b = []
    for i in iterable[:-1]:
        a += 1
        if i != iterable[a]:
            b.append(i)
    b.append(iterable[-1])
    return b

if __name__ == '__main__':
    print(unique_in_order(''))
