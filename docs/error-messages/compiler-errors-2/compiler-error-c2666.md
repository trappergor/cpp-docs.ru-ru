---
title: Ошибка компилятора C2666
ms.date: 11/04/2016
f1_keywords:
- C2666
helpviewer_keywords:
- C2666
ms.assetid: 78364d15-c6eb-439a-9088-e04a0176692b
ms.openlocfilehash: ebe41a4c4aa090e609d3352635d4e1fc06e22454
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743221"
---
# <a name="compiler-error-c2666"></a>Ошибка компилятора C2666

"идентификатор": числовые перегрузки имеют похожие преобразования

Перегруженная функция или оператор неоднозначно.   Списки формальных параметров могут оказаться слишком похожими, чтобы компилятор мог устранить неоднозначность.  Чтобы устранить эту ошибку, явно приведите один или несколько фактических параметров.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C2666:

```cpp
// C2666.cpp
struct complex {
   complex(double);
};

void h(int,complex);
void h(double, double);

int main() {
   h(3,4);   // C2666
}
```

Эта ошибка также может быть вызвана работой по согласованности компилятора, выполненной для Visual Studio .NET 2003:

- Бинарные операторы и пользовательские преобразования в типы указателей

- Преобразование квалификации не совпадает с преобразованием идентификаторов

Для бинарных операторов \<, > — \<=, and > переданный параметр теперь неявно преобразуется в тип операнда, если тип параметра определяет определяемый пользователем оператор преобразования для преобразования в тип операнда. Теперь существует возможность неоднозначности.

Для кода, который допустим в версиях Visual Studio .NET 2003 и Visual Studio .NET Visual C++, вызовите оператор класса явным образом с помощью синтаксиса функции.

```cpp
// C2666b.cpp
#include <string.h>
#include <stdio.h>

struct T
{
    T( const T& copy )
    {
        m_str = copy.m_str;
    }

    T( const char* str )
    {
        int iSize = (strlen( str )+ 1);
        m_str = new char[ iSize ];
        if (m_str)
            strcpy_s( m_str, iSize, str );
    }

    bool operator<( const T& RHS )
    {
        return m_str < RHS.m_str;
    }

    operator char*() const
    {
        return m_str;
    }

    char* m_str;
};

int main()
{
    T str1( "ABCD" );
    const char* str2 = "DEFG";

    // Error - Ambiguous call to operator<()
    // Trying to convert str1 to char* and then call
    // operator<( const char*, const char* )?
    //  OR
    // trying to convert str2 to T and then call
    // T::operator<( const T& )?

    if( str1 < str2 )   // C2666

    if ( str1.operator < ( str2 ) )   // Treat str2 as type T
        printf_s("str1.operator < ( str2 )\n");

    if ( str1.operator char*() < str2 )   // Treat str1 as type char*
        printf_s("str1.operator char*() < str2\n");
}
```

Следующий пример приводит к возникновению ошибки C2666

```cpp
// C2666c.cpp
// compile with: /c

enum E
{
    E_A,   E_B
};

class A
{
    int h(const E e) const {return 0; }
    int h(const int i) { return 1; }
    // Uncomment the following line to resolve.
    // int h(const E e) { return 0; }

    void Test()
    {
        h(E_A);   // C2666
        h((const int) E_A);
        h((int) E_A);
    }
};
```
