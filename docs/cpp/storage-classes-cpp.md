---
title: Классы хранения (C++)
description: В C++ статические, внешние и thread_local ключевые слова определяют время существования, компоновку и расположение памяти для переменной или функции.
ms.date: 12/11/2019
f1_keywords:
- thread_local_cpp
- static_cpp
- register_cpp
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
ms.openlocfilehash: c3fc87980d1fd0af5b803a8e590855f6429c847e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213168"
---
# <a name="storage-classes"></a>Классы хранения

*Класс хранения* в контексте объявлений переменных C++ — это описатель типа, который управляет временем существования, компоновкой и расположением памяти объектов. Каждый объект может иметь только один класс хранения. Переменные, определенные в блоке, имеют автоматическое хранение, если не указано иное с помощью **`extern`** **`static`** **`thread_local`** описателей, или. Автоматически создаваемые объекты и переменные не имеют компоновки. Они не доступны для кода за пределами блока. Память выделяется для них автоматически, когда выполнение входит в блок и освобождается при выходе из блока.

**Примечания**

1. Ключевое слово [mutable](../cpp/mutable-data-members-cpp.md) может рассматриваться как описатель класса хранения. Однако он доступен только в списке членов в определении класса.

1. **Visual Studio 2010 и более поздние версии:** **`auto`** Ключевое слово больше не является описателем класса хранения C++, а **`register`** ключевое слово является устаревшим. **Visual Studio 2017 версии 15,7 и более поздних версий:** (доступно с [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) ): **`register`** ключевое слово удаляется из языка C++.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="static"></a><a name="static"></a> `static`

**`static`** Ключевое слово можно использовать для объявления переменных и функций в глобальной области видимости, области пространства имен и области класса. Статические переменные также могут быть объявлены в локальной области видимости.

Статическая длительность означает, что объект или переменная выделяется при запуске программы и освобождается при ее завершении. Внешняя компоновка означает, что имя переменной видно за пределами файла, в котором эта переменная объявлена. Внутренняя компоновка означает, что имя не видно за пределами файла, в котором объявлена переменная. По умолчанию объект или переменная, определенные в глобальном пространстве имен, имеют статическую длительность и внешнюю компоновку. **`static`** Ключевое слово можно использовать в следующих ситуациях.

1. При объявлении переменной или функции в области видимости файла (глобальной и/или области пространства имен) **`static`** ключевое слово указывает, что переменная или функция имеет внутреннюю компоновку. При объявлении переменной она имеет статическую длительность и компилятор инициализирует ее со значением 0, если не указано другое значение.

1. При объявлении переменной в функции **`static`** ключевое слово указывает, что переменная удерживает свое состояние между вызовами этой функции.

1. При объявлении члена данных в объявлении класса **`static`** ключевое слово указывает, что одна копия элемента совместно используется всеми экземплярами класса. Статические данные-член должны быть определены в области видимости файла. Целочисленный член данных, объявляемый как, **`const static`** может иметь инициализатор.

1. При объявлении функции-члена в объявлении класса **`static`** ключевое слово указывает, что функция совместно используется всеми экземплярами класса. Статическая функция-член не может получить доступ к члену экземпляра, так как функция не имеет неявного **`this`** указателя. Для доступа к члену экземпляра следует объявить функцию с параметром, являющимся указателем или ссылкой на экземпляр.

1. Объявление членов объединения как статических невозможно. Однако глобально объявленное анонимное объединение должно быть явно объявлено **`static`** .

В этом примере показано, как переменная **`static`** , объявленная в функции, удерживает свое состояние между вызовами этой функции.

```cpp
// static1.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
void showstat( int curr ) {
   static int nStatic;    // Value of nStatic is retained
                          // between each function call
   nStatic += curr;
   cout << "nStatic is " << nStatic << endl;
}

int main() {
   for ( int i = 0; i < 5; i++ )
      showstat( i );
}
```

```Output
nStatic is 0
nStatic is 1
nStatic is 3
nStatic is 6
nStatic is 10
```

В этом примере показано использование **`static`** в классе.

```cpp
// static2.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class CMyClass {
public:
   static int m_i;
};

int CMyClass::m_i = 0;
CMyClass myObject1;
CMyClass myObject2;

int main() {
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;

   myObject1.m_i = 1;
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;

   myObject2.m_i = 2;
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;

   CMyClass::m_i = 3;
   cout << myObject1.m_i << endl;
   cout << myObject2.m_i << endl;
}
```

```Output
0
0
1
1
2
2
3
3
```

В этом примере показана локальная переменная, объявленная **`static`** в функции-члене. **`static`** Переменная доступна всей программе; все экземпляры типа совместно используют одну и ту же копию **`static`** переменной.

```cpp
// static3.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
struct C {
   void Test(int value) {
      static int var = 0;
      if (var == value)
         cout << "var == value" << endl;
      else
         cout << "var != value" << endl;

      var = value;
   }
};

int main() {
   C c1;
   C c2;
   c1.Test(100);
   c2.Test(100);
}
```

```Output
var != value
var == value
```

Начиная с C++ 11, **`static`** Инициализация локальной переменной гарантирует потокобезопасность. Эта функция иногда называется *магической статичностью*. Однако в многопоточном приложении все последующие назначения должны быть синхронизированы. Потокобезопасную функцию статической инициализации можно отключить с помощью [`/Zc:threadSafeInit-`](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) флага, чтобы избежать зависимости от CRT.

## <a name="extern"></a><a name="extern"></a> `extern`

Объекты и переменные, объявленные как **`extern`** объявляют объект, который определен в другой записи преобразования или во внешней области видимости как внешняя компоновка. Дополнительные сведения см. в разделе [`extern`](extern-cpp.md) и [Преобразование единиц и компоновки](program-and-linkage-cpp.md).

## <a name="thread_local-c11"></a><a name="thread_local"></a>`thread_local`(C++ 11)

Переменная, объявленная с **`thread_local`** описателем, доступна только в том потоке, в котором он создан. Переменная создается при создании потока и уничтожается при его уничтожении. Каждый поток имеет свою собственную копию переменной. В Windows **`thread_local`** функционально эквивалентен атрибуту, характерному для Microsoft [`__declspec( thread )`](../cpp/thread.md) .

```cpp
thread_local float f = 42.0; // Global namespace. Not implicitly static.

struct S // cannot be applied to type definition
{
    thread_local int i; // Illegal. The member must be static.
    thread_local static char buf[10]; // OK
};

void DoSomething()
{
    // Apply thread_local to a local variable.
    // Implicitly "thread_local static S my_struct".
    thread_local S my_struct;
}
```

Обратите внимание на **`thread_local`** описатель:

- Динамически инициализированные локальные переменные потока в библиотеках DLL могут быть неправильно инициализированы во всех вызывающих потоках. Дополнительные сведения см. на веб-сайте [`thread`](thread.md).

- **`thread_local`** Спецификатор можно сочетать с **`static`** или **`extern`** .

- Можно применять **`thread_local`** только к объявлениям и определениям данных; **`thread_local`** не может использоваться в объявлениях или определениях функций.

- Можно указать **`thread_local`** только для элементов данных со статической длительностью хранилища. Сюда входят глобальные объекты данных ( **`static`** и **`extern`** ), локальные статические объекты и статические члены данных классов. Объявленная локальная переменная **`thread_local`** неявно является статической, если не предоставлен другой класс хранения; иными словами, в области видимости блока **`thread_local`** эквивалентна **`thread_local static`** .

- Необходимо указать **`thread_local`** как для объявления, так и для определения локального объекта потока, будь то объявление и определение происходят в одном и том же файле или в отдельных файлах.

В Windows **`thread_local`** функционально эквивалентен [`__declspec(thread)`](../cpp/thread.md) за исключением того, что *`*__declspec(thread)`* * может применяться к определению типа и является допустимым в коде на языке C. Везде, где это возможно, используйте, **`thread_local`** так как он является частью стандарта C++ и, таким образом, более переносим.

## <a name="register"></a><a name="register"></a>зарегистрировать

**Visual Studio 2017 версии 15,3 и более поздних версий** (доступно с [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) ): **`register`** ключевое слово больше не является поддерживаемым классом хранения. Ключевое слово по-прежнему зарезервировано в стандарте для будущего использования.

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>Пример: автоматическая и статическая инициализация

Локальные автоматически создаваемые объекты или переменные инициализируются каждый раз, когда поток элемента управления достигает их определения. Локальные статические объекты или переменные инициализируются, когда поток элемента управления достигает их определения в первый раз.

Рассмотрим следующий пример, в котором определяется класс, который регистрирует инициализацию и удаление объектов, а затем определяет три объекта: `I1`, `I2` и `I3`.

```cpp
// initialization_of_objects.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>
using namespace std;

// Define a class that logs initializations and destructions.
class InitDemo {
public:
    InitDemo( const char *szWhat );
    ~InitDemo();

private:
    char *szObjName;
    size_t sizeofObjName;
};

// Constructor for class InitDemo
InitDemo::InitDemo( const char *szWhat ) :
    szObjName(NULL), sizeofObjName(0) {
    if ( szWhat != 0 && strlen( szWhat ) > 0 ) {
        // Allocate storage for szObjName, then copy
        // initializer szWhat into szObjName, using
        // secured CRT functions.
        sizeofObjName = strlen( szWhat ) + 1;

        szObjName = new char[ sizeofObjName ];
        strcpy_s( szObjName, sizeofObjName, szWhat );

        cout << "Initializing: " << szObjName << "\n";
    }
    else {
        szObjName = 0;
    }
}

// Destructor for InitDemo
InitDemo::~InitDemo() {
    if( szObjName != 0 ) {
        cout << "Destroying: " << szObjName << "\n";
        delete szObjName;
    }
}

// Enter main function
int main() {
    InitDemo I1( "Auto I1" ); {
        cout << "In block.\n";
        InitDemo I2( "Auto I2" );
        static InitDemo I3( "Static I3" );
    }
    cout << "Exited block.\n";
}
```

```Output
Initializing: Auto I1
In block.
Initializing: Auto I2
Initializing: Static I3
Destroying: Auto I2
Exited block.
Destroying: Auto I1
Destroying: Static I3
```

В этом примере показано, как и когда `I1` `I2` инициализируются объекты, и, а также `I3` когда они уничтожаются.

Существует несколько моментов, которые необходимо учитывать в программе:

- Во-первых, `I1` и `I2` автоматически удаляются, когда поток элемента управления выходит за пределы блока, в котором они определены.

- Во-вторых, в C++ не обязательно объявлять объекты или переменные в начале блока. Более того, эти объекты инициализируются, только если поток элемента управления достигает их определения. ( `I2` и `I3` являются примерами таких определений.) Выходные данные показываются точно при инициализации.

- Наконец, статические локальные переменные, например `I3`, сохраняют свои значения длительности программы, но удаляются при завершении работы программы.

## <a name="see-also"></a>См. также раздел

[Объявления и определения](../cpp/declarations-and-definitions-cpp.md)
