def first_word(text: str) -> str:
    """
        returns the first word in a given text.
    """
    a = ''    # заводим пустую строку
    b = 0     # заводим счётчик
    for i in text:    # перебираем текст
        b += 1      # увеличиваем счётчик
        if i.isalpha() or i == "'":     #если буква или апостроф
            a = a + i       # добавляем в строку
            if i == ' ':     # если пробел
                return a    # возвращаем слово
        elif i == ' ' and len(a) >= 1:  
            return a
        else:
            if len(a) >= 1:
                return a
            else:
                text = text[b:]
                b = 0
    return text


if __name__ == '__main__':
    print("Example:")
    print(first_word("Hello world"))
    
    # These "asserts" are used for self-checking and not for an auto-testing
    assert first_word("Hello world") == "Hello"
    assert first_word(" a word ") == "a"
    assert first_word("don't touch it") == "don't"
    assert first_word("greetings, friends") == "greetings"
    assert first_word("... and so on ...") == "and"
    assert first_word("hi") == "hi"
    assert first_word("Hello.World") == "Hello"
    print("Coding complete? Click 'Check' to earn cool rewards!")
