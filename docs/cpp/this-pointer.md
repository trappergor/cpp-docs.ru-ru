---
title: Этот указатель | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- this_cpp
dev_langs:
- C++
helpviewer_keywords:
- nonstatic member functions [C++]
- pointers, to class instance
- this pointer
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e6a1df3bb262a814c641f5bfbcee070ec5de344
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="this-pointer"></a>Указатель this
**Это** указатель является указателем, доступный только в нестатических функциях-членах **класса**, `struct`, или **объединение** типа. Он указывает на объект, для которого вызывается функция-член. Статические функции-члены имеют **это** указателя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      this   
this->member-identifier  
```  
  
## <a name="remarks"></a>Примечания  
 Объект **это** указатель не является частью самого объекта не отражается в результате `sizeof` инструкции в объекте. Вместо этого при вызове нестатической функции-члена для объекта компилятор передает адрес объекта в функцию в качестве скрытого аргумента. Например, при вызове следующей функции  
  
```  
myDate.setMonth( 3 );  
```  
  
 можно интерпретировать следующим образом:  
  
```  
setMonth( &myDate, 3 );  
```  
  
 Адрес объекта доступен в функции-члена как **это** указателя. Большинство использования **это** являются неявными. Допустимо, хотя не рекомендуется, чтобы явно использовать **это** при ссылке на члены класса. Пример:  
  
```  
void Date::setMonth( int mn )  
{  
   month = mn;            // These three statements  
   this->month = mn;      // are equivalent  
   (*this).month = mn;  
}  
```  
  
 Выражение `*this` обычно используется для возврата текущего объекта из функции-члена.  
  
```  
return *this;  
```  
  
 **Это** указатель также используется для защиты от рекурсивной ссылки:  
  
```  
if (&Object != this) {  
// do not execute in cases of self-reference  
```  
  
> [!NOTE]
>  Поскольку **это** указатель неизменяемый, назначения, чтобы **это** не допускаются. Более ранних реализациях C++ допускается назначений, **это**.  
  
 В некоторых случаях **это** указатель используется непосредственно — например, для работы с данными себя структуры, где требуется адрес текущего объекта.  
  
## <a name="example"></a>Пример  
  
```  
// this_pointer.cpp  
// compile with: /EHsc  
  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
  
class Buf   
{  
public:  
    Buf( char* szBuffer, size_t sizeOfBuffer );  
    Buf& operator=( const Buf & );  
    void Display() { cout << buffer << endl; }  
  
private:  
    char*   buffer;  
    size_t  sizeOfBuffer;  
};  
  
Buf::Buf( char* szBuffer, size_t sizeOfBuffer )  
{  
    sizeOfBuffer++; // account for a NULL terminator  
  
    buffer = new char[ sizeOfBuffer ];  
    if (buffer)  
    {  
        strcpy_s( buffer, sizeOfBuffer, szBuffer );  
        sizeOfBuffer = sizeOfBuffer;  
    }  
}  
  
Buf& Buf::operator=( const Buf &otherbuf )   
{  
    if( &otherbuf != this )   
    {  
        if (buffer)  
            delete [] buffer;  
  
        sizeOfBuffer =  strlen( otherbuf.buffer ) + 1;   
        buffer = new char[sizeOfBuffer];  
        strcpy_s( buffer, sizeOfBuffer, otherbuf.buffer );  
    }  
    return *this;  
}  
  
int main()  
{  
    Buf myBuf( "my buffer", 10 );  
    Buf yourBuf( "your buffer", 12 );  
  
    // Display 'my buffer'  
    myBuf.Display();  
  
    // assignment opperator  
    myBuf = yourBuf;  
  
    // Display 'your buffer'  
    myBuf.Display();  
}  
```  
  
```Output  
my buffer  
your buffer  
```  
  
## <a name="type-of-the-this-pointer"></a>Тип указателя this  
 **Это** в объявлении функции, можно ли изменить тип указателя **const** и `volatile` ключевые слова. Для того чтобы объявить функцию с атрибутами, имеющими одно или оба этих ключевых слова, добавьте нужные ключевые слова после списка аргументов функции.  
  
 Рассмотрим следующий пример.  
  
```  
// type_of_this_pointer1.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 Предыдущий код объявляет функцию-член, `X`, в котором **это** обрабатывается как указатель **const** указатель **const** объекта. Сочетание *список cv-mod* можно использовать параметры, но эти модификаторы всегда изменяют объект, на который указывает **это**, а не **это** сам указатель. Таким образом, в следующем примере объявляется функция `X`; **это** указатель **const** указатель **const** объекта:  
  
```  
// type_of_this_pointer2.cpp  
class Point  
{  
    unsigned X() const;  
};  
int main()  
{  
}  
```  
  
 Тип **это** в члене функции описан с помощью следующего синтаксиса, где *список cv квалификаторов* определяется из декларатора функций-членов и может быть **const**или **volatile** (или оба), и *типа класса* имя класса:  
  
 *тип класса [cv список квалификаторов]* **\* const это**  
  
 Другими словами **это** всегда является указателем const; не может быть переназначен.  **Const** или `volatile` квалификаторы, используется в объявлении члена функции применяются к экземпляру класса, на который указывает **это** в области видимости данной функции.  
  
 В следующей таблице приведены дополнительные сведения о том, как работают эти модификаторы.  
  
### <a name="semantics-of-this-modifiers"></a>Значение модификаторов  
  
|Модификатор|Значение|  
|--------------|-------------|  
|**const**|Не удается изменить элемент данных; не удается вызвать функции-члены, не **const**.|  
|`volatile`|Данные-члены загружаются из памяти при каждом обращении. Ряд оптимизаций отключается.|  
  
 Это ошибка для передачи **const** объекта на функцию-член, который не **const**. Аналогично, ошибкой будет передать объект `volatile` функции-члену без модификатора `volatile`.  
  
 Функции-члены объявлены как **const** не удается изменить элемент данных — в таких функциях **это** указателя — указатель на **const** объекта.  
  
> [!NOTE]
>  Конструкторы и деструкторы не могут объявляться как **const** или `volatile`. Тем не менее, их можно вызывать для **const** или `volatile` объектов.  
  
## <a name="see-also"></a>См. также  
 [Ключевые слова](../cpp/keywords-cpp.md)   
 