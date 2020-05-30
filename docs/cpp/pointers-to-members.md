---
title: Указатели на члены
ms.date: 11/04/2016
helpviewer_keywords:
- declarations, pointers
- class members [C++], pointers to
- pointers, to members
- members [C++], pointers to
- pointers, declarations
ms.assetid: f42ddb79-9721-4e39-95b1-c56b55591f68
ms.openlocfilehash: 75bd29310d64b0309ac48be053aa43cc0084aa2d
ms.sourcegitcommit: 1a8fac06478da8bee1f6d70e25afbad94144af1a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/30/2020
ms.locfileid: "84226095"
---
# <a name="pointers-to-members"></a>Указатели на члены

Объявления указателей на члены — это особый случай объявлений указателей.  Они объявляются с помощью следующей последовательности:

> *спецификаторы класса хранения*<sub>необязательно</sub> *— Квалификаторы*<sub>opt</sub> не заменяют *спецификаторы типа "описатель* *qualified-name* "<sub>opt</sub> квалификатора *MS-модификаторов*opt **`::*`** *cv-qualifiers*<sub>opt</sub> *identifier* *pm-initializer*<sub>opt</sub>**`;`**

1. Спецификатор объявления:

   - Необязательный спецификатор класса хранения.

   - Необязательные спецификаторы **const** и **volatile** .

   - Спецификатор типа: имя типа. Это тип элемента, на который указывает, а не класс.

1. Декларатор:

   - Необязательный модификатор, используемый в системах Microsoft. Дополнительные сведения см. в разделе [модификаторы, зависящие от Майкрософт](../cpp/microsoft-specific-modifiers.md).

   - Полное имя класса, содержащего члены, на которые должен указывать указатель.

   - __`::`__ Оператор.

   - __`*`__ Оператор.

   - Необязательные спецификаторы **const** и **volatile** .

   - Идентификатор, задающий имя указателя на член.

1. Необязательный инициализатор указателя на член:

   - **`=`** Оператор.

   - **`&`** Оператор.

   - Полное имя класса.

   - __`::`__ Оператор.

   - Имя не являющегося статическим члена класса соответствующего типа.

Как обычно, в одном объявлении допускается несколько деклараторов (и любые связанные инициализаторы). Указатель на член может не указывать на статический член класса, член ссылочного типа или **`void`** .

Указатель на член класса отличается от обычного указателя: он имеет как информацию о типе для типа элемента, так и для класса, которому принадлежит элемент. Обычный указатель идентифицирует только один объект в памяти (содержит адрес этого объекта). Указатель на член класса идентифицирует этот член в любом экземпляре класса. В следующем примере объявляется класс `Window` и несколько указателей на данные-член.

```cpp
// pointers_to_members1.cpp
class Window
{
public:
   Window();                               // Default constructor.
   Window( int x1, int y1,                 // Constructor specifying
   int x2, int y2 );                       // Window size.
   bool SetCaption( const char *szTitle ); // Set window caption.
   const char *GetCaption();               // Get window caption.
   char *szWinCaption;                     // Window caption.
};

// Declare a pointer to the data member szWinCaption.
char * Window::* pwCaption = &Window::szWinCaption;
int main()
{
}
```

В предыдущем примере `pwCaption` — это указатель на любой член класса `Window` , который имеет тип `char*` . `pwCaption` имеет тип `char * Window::*`. В следующем фрагменте кода объявляются указатели на функции-члены `SetCaption` и `GetCaption`.

```cpp
const char * (Window::* pfnwGC)() = &Window::GetCaption;
bool (Window::* pfnwSC)( const char * ) = &Window::SetCaption;
```

Указатели `pfnwGC` и `pfnwSC` указывают на функции `GetCaption` и `SetCaption` класса `Window` соответственно. Код копирует информацию непосредственно в заголовок окна с помощью указателя на член `pwCaption`:

```cpp
Window  wMainWindow;
Window *pwChildWindow = new Window;
char   *szUntitled    = "Untitled -  ";
int     cUntitledLen  = strlen( szUntitled );

strcpy_s( wMainWindow.*pwCaption, cUntitledLen, szUntitled );
(wMainWindow.*pwCaption)[cUntitledLen - 1] = '1';     // same as
// wMainWindow.SzWinCaption [cUntitledLen - 1] = '1';
strcpy_s( pwChildWindow->*pwCaption, cUntitledLen, szUntitled );
(pwChildWindow->*pwCaption)[cUntitledLen - 1] = '2'; // same as
// pwChildWindow->szWinCaption[cUntitledLen - 1] = '2';
```

Разница между **`.*`** **`->*`** операторами и (операторами указателей на члены) заключается в том, что **`.*`** оператор выбирает члены по ссылке на объект или объект, а **`->*`** оператор выбирает члены с помощью указателя. Дополнительные сведения об этих операторах см. [в разделе выражения с операторами указателей на члены](../cpp/pointer-to-member-operators-dot-star-and-star.md).

Результатом операторов указателя на член является тип элемента. В этом случае он выглядит так: `char *`.

В следующем фрагменте кода функции-члены `GetCaption` и `SetCaption` вызываются с использованием указателей на члены.

```cpp
// Allocate a buffer.
enum {
    sizeOfBuffer = 100
};
char szCaptionBase[sizeOfBuffer];

// Copy the main window caption into the buffer
//  and append " [View 1]".
strcpy_s( szCaptionBase, sizeOfBuffer, (wMainWindow.*pfnwGC)() );
strcat_s( szCaptionBase, sizeOfBuffer, " [View 1]" );
// Set the child window's caption.
(pwChildWindow->*pfnwSC)( szCaptionBase );
```

## <a name="restrictions-on-pointers-to-members"></a>Ограничения указателей на члены

Адрес статического элемента не является указателем на элемент. Это обычный указатель на один экземпляр статического элемента. Для всех объектов данного класса существует только один экземпляр статического элемента. Это означает, что можно использовать обычные операторы address-of ( **&** ) и разыменование ( <strong>\*</strong> ).

## <a name="pointers-to-members-and-virtual-functions"></a>Указатели на члены и виртуальные функции

Вызов виртуальной функции с помощью функции указателя на член работает так же, как если бы функция вызывалась напрямую. Правильная функция ищется в таблице v-table и вызывается.

Ключ для виртуальных функций, работающих как обычно, вызывает их через указатель на базовый класс. (Дополнительные сведения о виртуальных функциях см. в разделе [виртуальные функции](../cpp/virtual-functions.md).)

В следующем коде показан вызов виртуальной функции через функцию указателя на член.

```cpp
// virtual_functions.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Base
{
public:
    virtual void Print();
};
void (Base::* bfnPrint)() = &Base::Print;
void Base::Print()
{
    cout << "Print function for class Base" << endl;
}

class Derived : public Base
{
public:
    void Print();  // Print is still a virtual function.
};

void Derived::Print()
{
    cout << "Print function for class Derived" << endl;
}

int main()
{
    Base   *bPtr;
    Base    bObject;
    Derived dObject;
    bPtr = &bObject;    // Set pointer to address of bObject.
    (bPtr->*bfnPrint)();
    bPtr = &dObject;    // Set pointer to address of dObject.
    (bPtr->*bfnPrint)();
}

// Output:
// Print function for class Base
// Print function for class Derived
```
