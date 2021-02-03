def words_order(text: str, words: list) -> bool:
    if len(words) == 1:
        words = ''.join(words)
        if text.find(words) > -1:
            return True
    if words[1:].count(words[0]) > 0:
        return False
    text = text.split()
    b = ''
    c = ''
    a = 0
    for i in text:
        if a < len(words):
            if i == words[a]:
                b += i
                a += 1
        else:
            continue
    for j in words:
        c += j
    if b == c:
        return True
    else:
        return False


if __name__ == '__main__':
    print("Example:")
    print(words_order('hi world world im here', ['world', 'world']))

    # These "asserts" are used for self-checking and not for an auto-testing
    assert words_order('hi world im here', ['world', 'here']) == True
    assert words_order('hi world im here', ['here', 'world']) == False
    assert words_order('hi world im here', ['world']) == True
    assert words_order('hi world im here',
 ['world', 'here', 'hi']) == False
    assert words_order('hi world im here',
 ['world', 'im', 'here']) == True
    assert words_order('hi world im here',
 ['world', 'hi', 'here']) == False
    assert words_order('hi world im here', ['world', 'world']) == False
    assert words_order('hi world im here',
 ['country', 'world']) == False
    assert words_order('hi world im here', ['wo', 'rld']) == False
    assert words_order('', ['world', 'here']) == False
    print("Coding complete? Click 'Check' to earn cool rewards!")
