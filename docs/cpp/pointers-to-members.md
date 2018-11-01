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
ms.openlocfilehash: ac8a1b43b3bf8bde8f910e72b601bf7d94e0d19d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480294"
---
# <a name="pointers-to-members"></a>Указатели на члены

Объявления указателей на члены — это особый случай объявлений указателей.  Они объявляются с помощью следующей последовательности:

```
[storage-class-specifiers] [cv-qualifiers] type-specifiers [ms-modifier]qualified-name ::* [cv-qualifiers] identifier
[= & qualified-name :: member-name];
```

1. Спецификатор объявления:
  - Необязательный спецификатор класса хранения.

  - Необязательный **const** и/или **volatile** спецификаторы.

  - Спецификатор типа: имя типа.  Это тип члена, на который должен указывать указатель, а не класс.

1. Декларатор:

  - Необязательный модификатор, используемый в системах Microsoft. Дополнительные сведения см. в разделе [модификаторы, используемые Microsoft](../cpp/microsoft-specific-modifiers.md).
1. Полное имя класса, содержащего члены, на которые должен указывать указатель.
  - Оператор ::.
  - <strong>\*</strong> Оператор.
  - Необязательный **const** и/или **volatile** спецификаторы.
  - Идентификатор, задающий имя указателя на член.

  - Необязательный инициализатор:
  - **=** Оператор.
  - **&** Оператор.
  - Полное имя класса.
  - Оператор `::`.
  - Имя нестатического члена класса соответствующего типа.
  - Как обычно, в одном объявлении допускается несколько деклараторов (и любые связанные инициализаторы).

Указатель на член класса отличается от обычного указателя, поскольку он содержит сведения о типе члена и типе класса, к которому принадлежит этот член. Обычный указатель идентифицирует только один объект в памяти (содержит адрес этого объекта). Указатель на член класса идентифицирует этот член в любом экземпляре класса. В следующем примере объявляется класс `Window` и несколько указателей на данные-член.

```cpp
// pointers_to_members1.cpp
class Window
{
public:
   Window();                               // Default constructor.
   Window( int x1, int y1,                 // Constructor specifying
   int x2, int y2 );                       //  window size.
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

В приведенном выше примере `pwCaption` является указателем на любой член класса `Window` , имеет тип `char*`. `pwCaption` имеет тип `char * Window::* `. В следующем фрагменте кода объявляются указатели на функции-члены `SetCaption` и `GetCaption`.

```cpp
const char * (Window::*pfnwGC)() = &Window::GetCaption;
bool (Window::*pfnwSC)( const char * ) = &Window::SetCaption;
```

Указатели `pfnwGC` и `pfnwSC` указывают на функции `GetCaption` и `SetCaption` класса `Window` соответственно. Код копирует информацию непосредственно в заголовок окна с помощью указателя на член `pwCaption`:

```cpp
Window wMainWindow;
Window *pwChildWindow = new Window;
char   *szUntitled    = "Untitled -  ";
int    cUntitledLen   = strlen( szUntitled );

strcpy_s( wMainWindow.*pwCaption, cUntitledLen, szUntitled );
(wMainWindow.*pwCaption)[cUntitledLen - 1] = '1';     //same as
//wMainWindow.SzWinCaption [cUntitledLen - 1] = '1';
strcpy_s( pwChildWindow->*pwCaption, cUntitledLen, szUntitled );
(pwChildWindow->*pwCaption)[cUntitledLen - 1] = '2'; //same as //pwChildWindow->szWinCaption[cUntitledLen - 1] = '2';
```

Разница между **.** <strong>\*</strong> и **->** <strong>\*</strong> операторов (операторов указателя на член) является то, что **.** <strong>\*</strong> оператор выбирает члены указанному объекту или ссылка на объект, тогда как **->** <strong>\*</strong> оператор выбирает члены с помощью указателя. (Дополнительные сведения об этих операторах см. в разделе [выражения с операторами указателя на член](../cpp/pointer-to-member-operators-dot-star-and-star.md).)

Результатом операторов указателя на член является тип члена — в этом случае `char *`.

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

Адрес статического члена не является указателем на член. Это обычный указатель на один экземпляр статического члена. Так как существует только один экземпляр статического члена для всех объектов данного класса, обычные взятия адреса (**&**) и разыменования (<strong>\*</strong>) можно использовать операторы.

## <a name="pointers-to-members-and-virtual-functions"></a>Указатели на члены и виртуальные функции

Вызов виртуальной функции через функцию указателя на член действует аналогично непосредственному вызову функции; соответствующая функция ищется в v-таблице и вызывается.

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
void (Base ::* bfnPrint)() = &Base :: Print;
void Base :: Print()
{
    cout << "Print function for class Base\n";
}

class Derived : public Base
{
    public:
    void Print();  // Print is still a virtual function.
};

void Derived :: Print()
{
    cout << "Print function for class Derived\n";
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

//Output: Print function for class Base
Print function for class Derived
```