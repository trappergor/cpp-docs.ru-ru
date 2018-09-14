---
title: Предупреждение (уровень 4) C4840 компилятора | Документация Майкрософт
ms.custom: ''
ms.date: 09/13/2018
ms.topic: error-reference
f1_keywords:
- C4840
dev_langs:
- C++
helpviewer_keywords:
- C4840
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0baf70ac7fd4d07958478d2eef455c7dc395e221
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601829"
---
# <a name="compiler-warning-level-4-c4840"></a>Компилятор C4840 предупреждение (уровень 4)

> непереносимое использование класса*тип*"как аргумент для функции с переменным числом аргументов
  
## <a name="remarks"></a>Примечания

Необходимо тривиально копируемых классов или структур, которые передаются в функцию с переменным числом аргументов. При передаче таких объектов компилятор просто выполняет побитовое копирование и не вызывает конструктор или деструктор.

Это предупреждение будет доступно в Visual Studio 2017.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4840 и показаны способы ее устранения:

```cpp
// C4840.cpp
// compile by using: cl /EHsc /W4 C4840.cpp
#include <stdio.h>

int main()
{
    struct S {
        S(int i) : i(i) {}
        S(const S& other) : i(other.i) {}
        operator int() { return i; }
    private:
        int i;
    } s(0);

    printf("%i\n", s); // warning C4840 : non-portable use of class 'main::S'
                       // as an argument to a variadic function
    // To correct the error, you can perform a static cast
    // to convert the object before passing it:
    printf("%i\n", static_cast<int>(s));
}
```

Для строк, созданных и управляемых с помощью `CStringW`, предоставленный `operator LPCWSTR()` следует использовать для приведения `CStringW` указатель на строку стиле C, ожидаемому строкой формата, который:

```cpp
    CStringW str1;
    CStringW str2;
    // ...
    str1.Format("%s", static_cast<LPCWSTR>(str2));
```