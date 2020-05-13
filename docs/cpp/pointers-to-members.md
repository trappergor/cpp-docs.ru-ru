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
ms.openlocfilehash: adffacc3ddc08679d7db4e17e027d8a7dbe8a92b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320320"
---
# <a name="pointers-to-members"></a>Указатели на члены

Объявления указателей на члены — это особый случай объявлений указателей.  Они объявлялись с помощью следующей последовательности:

> *хранение-класс-спецификаторы*<sub>выбрать</sub> *cv-квалификаторов*<sub>выбрать</sub> *тип-specifier* *мс-модификатор*<sub>выбрать</sub> *квалифицированных-имя* **`::*`** *cv-квалификаторов*<sub>выбрать</sub> *идентификатор* *PM-initializer*<sub>выбрать</sub>**`;`**

1. Спецификатор объявления:

   - Необязательный спецификатор класса хранения.

   - Дополнительные **конст и** **летучих** специфики.

   - Спецификатор типа: имя типа. Это тип участника, на который следует указать, а не класс.

1. Декларатор:

   - Необязательный модификатор, используемый в системах Microsoft. Для получения дополнительной информации [см.](../cpp/microsoft-specific-modifiers.md)

   - Полное имя класса, содержащего члены, на которые должен указывать указатель.

   - Оператор. __`::`__

   - Оператор. __`*`__

   - Дополнительные **конст и** **летучих** специфики.

   - Идентификатор, задающий имя указателя на член.

1. Дополнительный инициализатор указателя на члена:

   - Оператор. **`=`**

   - Оператор. **`&`**

   - Полное имя класса.

   - Оператор. __`::`__

   - Имя нестатического члена класса соответствующего типа.

Как обычно, в одном объявлении допускается несколько деклараторов (и любые связанные инициализаторы). Указатель для участника не может указывать на статического члена класса, **`void`** члена типов ссылки или .

Указатель для члена класса отличается от обычного указателя: он имеет как информацию о типе члена, так и для класса, к которому принадлежит участник. Обычный указатель идентифицирует только один объект в памяти (содержит адрес этого объекта). Указатель на член класса идентифицирует этот член в любом экземпляре класса. В следующем примере объявляется класс `Window` и несколько указателей на данные-член.

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

В предыдущем примере `pwCaption` указатель на любой `Window` член класса `char*`типа . `pwCaption` имеет тип `char * Window::*`. В следующем фрагменте кода объявляются указатели на функции-члены `SetCaption` и `GetCaption`.

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

Разница между **`.*`** операторами и **`->*`** операторами (операторами указателя **`.*`** на членов) заключается в том, **`->*`** что оператор выбирает членов, учитывая ссылку на объект или объект, в то время как оператор выбирает членов через указатель. Для получения дополнительной информации об этих [операторах см.](../cpp/pointer-to-member-operators-dot-star-and-star.md)

Результатом оператора указателей к члену является тип участника. В этом случае он выглядит так: `char *`.

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

Адрес статического участника не является указателем на участника. Это обычный указатель на один экземпляр статического члена. Только один экземпляр статического члена существует для всех объектов данного класса. Это означает, что вы можете**&** использовать обычный<strong>\*</strong>адрес () и dereference ( ) операторов.

## <a name="pointers-to-members-and-virtual-functions"></a>Указатели на члены и виртуальные функции

Вызов виртуальной функции через функцию указателя к члену работает так, как если бы функция была вызвана напрямую. Правильная функция просматривается в v-таблице и вызывается.

Ключ для виртуальных функций, работающих как обычно, вызывает их через указатель на базовый класс. (Для получения дополнительной информации о виртуальных функциях [см.](../cpp/virtual-functions.md)

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
