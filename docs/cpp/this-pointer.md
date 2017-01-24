---
title: "Указатель this | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "this"
  - "this_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "нестатические функции-члены"
  - "указатели, к экземпляру класса"
  - "указатель this"
ms.assetid: 92e3256a-4ad9-4d46-8be1-d77fad90791f
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Указатель this
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указатель **this** доступен только в нестатических функциях\-членах типа **class**, `struct` или **union**.  Он указывает на объект, для которого вызывается функция\-член.  Статические функции\-члены не имеют указатель **this**.  
  
## Синтаксис  
  
```  
  
        this   
this->member-identifier  
```  
  
## Заметки  
 Указатель **this** объекта не является частью самого объекта и не отражается в результате оператора `sizeof` объекта.  Вместо этого при вызове нестатической функции\-члена для объекта компилятор передает адрес объекта в функцию в качестве скрытого аргумента.  Например, при вызове следующей функции  
  
```  
myDate.setMonth( 3 );  
```  
  
 можно интерпретировать следующим образом:  
  
```  
setMonth( &myDate, 3 );  
```  
  
 Адрес объекта доступен из функции\-члена как указатель **this**.  В большинстве случаев указатель **this** используется неявно.  Явное использование указателя **this** при ссылке на члены класса допустимо, хотя не рекомендуется.  Пример:  
  
```  
void Date::setMonth( int mn )  
{  
   month = mn;            // These three statements  
   this->month = mn;      // are equivalent  
   (*this).month = mn;  
}  
```  
  
 Выражение `*this` обычно используется для возврата текущего объекта из функции\-члена.  
  
```  
return *this;  
```  
  
 Указатель **this** также используется для защиты от рекурсивной ссылки.  
  
```  
if (&Object != this) {  
// do not execute in cases of self-reference  
```  
  
> [!NOTE]
>  Поскольку указатель **this** неизменяемый, назначения указателю **this** не допускаются.  В более ранних реализациях C\+\+ назначения указателю **this** допускались.  
  
 Иногда указатель **this** используется непосредственно, например для управления структурами данных, ссылающимися на самих себя, когда требуется адрес текущего объекта.  
  
## Пример  
  
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
  
  **мой буфер**  
**ваш буфер**   
## Тип указателя this  
 Тип указателя **this** в объявлении функции можно изменить при помощи ключевых слов **const** и `volatile`.  Для того чтобы объявить функцию с атрибутами, имеющими одно или оба этих ключевых слова, добавьте нужные ключевые слова после списка аргументов функции.  
  
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
  
 В приведенном выше примере объявляется функция\-член `X`, в которой указатель **this** обрабатывается как указатель **const** на объект **const**.  Можно указать *список\-модификаторов\-const\-volatile*, но эти модификаторы всегда изменяют объект, на который указывает указатель **this**, а не сам указатель **this**.  Таким образом, в следующем примере объявляется функция `X`; указатель **this** является указателем **const** и указывает на объект **const**:  
  
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
  
 Тип указателя **this** в функции\-члене описывается следующим синтаксисом, где *список\_модификаторов\_const\_volatile* определяется исходя из декларатора функций\-членов и может иметь модификатор **const** или **volatile** \(или оба одновременно\), а *тип\_класса* означает имя класса:  
  
 *\[список\_квалификаторов\_const\_volatile\] тип\_класса* **\* const this**  
  
 Иными словами, указатель **this** всегда является указателем const и не может быть переназначен.  Квалификаторы **const** и `volatile`, используемые в объявлении функции\-члена, применяются к экземпляру класса, на который указывает указатель **this** в области видимости этой функции.  
  
 В следующей таблице приведены дополнительные сведения о том, как работают эти модификаторы.  
  
### Значение модификаторов  
  
|Модификатор|Значение|  
|-----------------|--------------|  
|**const**|Не может менять данные\-члены. Не может вызывать функции\-члены, которые не имеют модификатора **const**.|  
|`volatile`|Данные\-члены загружаются из памяти при каждом обращении. Ряд оптимизаций отключается.|  
  
 Передать объект **const** функции\-члену без квалификатора **const** будет ошибкой.  Аналогично, ошибкой будет передать объект `volatile` функции\-члену без модификатора `volatile`.  
  
 Функции\-члены, объявленные как **const**, не могут изменять данные\-члены — в этих функциях указатель **this** является указателем на объект **const**.  
  
> [!NOTE]
>  Конструкторы и деструкторы не могут объявляться как **const** или `volatile`.  Однако их можно вызывать для объектов **const** и `volatile`.  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Тип указателя this](../misc/type-of-this-pointer.md)   
 [Сопоставление аргументов и указатель this](../misc/argument-matching-and-the-this-pointer.md)