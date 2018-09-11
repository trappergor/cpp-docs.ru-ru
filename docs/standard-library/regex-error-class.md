---
title: Класс regex_error | Документы Майкрософт
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- regex/std::regex_error
- regex/std::regex_error::code
dev_langs:
- C++
helpviewer_keywords:
- regex_error class
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7358af41e1a7172daec619bec3e701ff4541fd0c
ms.sourcegitcommit: 27b5712badd09a09c499d887e2e4cf2208a28603
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2018
ms.locfileid: "44384986"
---
# <a name="regexerror-class"></a>Класс regex_error

Сообщает о неверном объекте basic_regex.

## <a name="syntax"></a>Синтаксис

```cpp
class regex_error
: public std::runtime_error
```

## <a name="remarks"></a>Примечания

Класс описывает объект исключения, создаваемый для уведомления об ошибке в построении или использовании объекта `basic_regex` .

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[regex_error](#regex_error)|Создает объект.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[Код](#code)|Возвращает код ошибки.|

## <a name="requirements"></a>Требования

**Заголовок:** \<regex>

**Пространство имен:** std

## <a name="example"></a>Пример

```cpp
// std__regex__regex_error.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
    {
    std::regex_error paren(std::regex_constants::error_paren);

    try
        {
        std::regex rx("(a");
        }
    catch (const std::regex_error& rerr)
        {
        std::cout << "regex error: "
            << (rerr.code() == paren.code() ? "unbalanced parentheses" : "")
            << std::endl;
        }
    catch (...)
        {
        std::cout << "unknown exception" << std::endl;
        }

    return (0);
    }
```

```Output
regex error: unbalanced parentheses
```

## <a name="code"></a>  regex_error::code

Возвращает код ошибки.

```cpp
regex_constants::error_code code() const;
```

### <a name="remarks"></a>Примечания

Функция-член возвращает значение, которое было передано в конструктор объекта.

## <a name="regex_error"></a>  regex_error::regex_error

Создает объект.

```cpp
regex_error(regex_constants::error_code error);
```

### <a name="parameters"></a>Параметры

*Ошибка*<br/>
Код ошибки.

### <a name="remarks"></a>Примечания

Конструктор создает объект, содержащий значение *ошибка*.

## <a name="see-also"></a>См. также

[\<regex>](../standard-library/regex.md)<br/>
[Класс regex_constants](../standard-library/regex-constants-class.md)<br/>
[Функции \<regex>](../standard-library/regex-functions.md)<br/>
[Класс regex_iterator](../standard-library/regex-iterator-class.md)<br/>
[Операторы \<regex>](../standard-library/regex-operators.md)<br/>
[Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)<br/>
[Класс regex_traits](../standard-library/regex-traits-class.md)<br/>
[Определения типов \<regex>](../standard-library/regex-typedefs.md)<br/>
