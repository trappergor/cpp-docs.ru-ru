---
title: Классы хранения (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- thread_local_cpp
- external_cpp
- static_cpp
- register_cpp
dev_langs:
- C++
helpviewer_keywords:
- storage classes [C++], basic concepts
ms.assetid: f10e1c56-6249-4eb6-b08f-09ab1eef1992
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e8f7939d42aa246c9b7d5924979357fb6301e726
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466589"
---
# <a name="storage-classes-c"></a>Классы хранения (C++)  
  
Объект *класс хранения* в контексте C++ объявления переменных — это описатель типа, который управляет временем существования, компоновкой и памяти расположения объектов. Каждый объект может иметь только один класс хранения. Переменные, определяемые в блоке, имеют автоматическое хранилище, если не указано с помощью **extern**, **статический**, или `thread_local` спецификаторы. Автоматически создаваемые объекты и переменные не имеют компоновки. Они не доступны для кода за пределами блока.  
  
**Примечания**  
  
1.  [Изменяемый](../cpp/mutable-data-members-cpp.md) ключевое слово может рассматриваться как спецификатор класса хранения. Однако он доступен только в списке членов в определении класса.  
  
2.  **Visual C++ 2010 и более поздних версий:** **автоматически** слово больше не является спецификатором класса хранения C++ и **зарегистрировать** ключевое слово является устаревшим. **Visual Studio 2017 версии 15.7 и более поздние версии:** (состав [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): **зарегистрировать** ключевое слово удаляется из языка C++.


```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="in-this-section"></a>Содержание

- [static](#static)
- [extern](#extern)
- [thread_local](#thread_local)

## <a name="static"></a> Static

**Статический** слово может использоваться для объявления переменных и функций в глобальной области, области видимости пространства имен и области видимости класса. Статические переменные также могут быть объявлены в локальной области видимости.

Статическая длительность означает, что объект или переменная выделяется при запуске программы и освобождается при ее завершении. Внешняя компоновка означает, что имя переменной видно за пределами файла, в котором эта переменная объявлена. Внутренняя компоновка означает, что имя не видно за пределами файла, в котором объявлена переменная. По умолчанию объект или переменная, определенные в глобальном пространстве имен, имеют статическую длительность и внешнюю компоновку. **Статический** слово может использоваться в следующих ситуациях.

1. При объявлении переменной или функции в области видимости файла (глобальные и/или области видимости пространства имен), **статический** ключевое слово указывает, что переменная или функция имеет внутреннюю компоновку. При объявлении переменной она имеет статическую длительность и компилятор инициализирует ее со значением 0, если не указано другое значение.

1. При объявлении переменной в функции, **статический** ключевое слово указывает, что переменная сохраняет свое состояние между вызовами этой функции.

1. При объявлении элемента данных в объявлении класса **статический** ключевое слово указывает, что одна копия элемента совместно используется всеми экземплярами класса. Статические данные-член должны быть определены в области видимости файла. Целочисленные данные-член, объявляемые как **const static** могут иметь инициализатор.

1. При объявлении функции-члена в объявлении класса **статический** ключевое слово указывает, что эта функция совместно используется всеми экземплярами класса. Статическая функция-член недоступен член экземпляра, так как функция имеет неявный **это** указатель. Для доступа к члену экземпляра следует объявить функцию с параметром, являющимся указателем или ссылкой на экземпляр.

1. Объявление членов объединения как статических невозможно. Однако глобально объявляемое Анонимное объединение должно явно объявляться **статических**.

В этом примере показано, как переменная, объявленная **статический** в функции, сохраняет свое состояние между вызовами этой функции.

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

В этом примере показано использование **статический** в классе.

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

В этом примере показано локальная переменная, объявленная **статический** в функции-члене. Статическая переменная доступна всей программе; все экземпляры типа будут совместно использовать одну и ту же копию этой переменной.

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

Начиная с версии C++ 11 для инициализации статических локальных переменных гарантируется потокобезопасность. Эта функция иногда называется *Волшебная статика*. Однако в многопоточном приложении все последующие назначения должны быть синхронизированы. Статическая инициализация поточно ориентированные функции можно отключить с помощью [/Zc: threadsafeinit](../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) флаг, чтобы избежать зависимости от CRT.

## <a name="extern"></a> extern

Объекты и переменные, объявленные как **extern** объявить объект, который определен в другой записи преобразования или во включающей области как имеющий внешнюю компоновку.

Объявление **const** переменных с **extern** класс хранения принудительно задают для переменной внешнюю компоновку. Инициализация **extern const** переменной допускается в определение. Инициализации в записях преобразования, отличных от записи, содержащей определение, дает неопределенные результаты. Дополнительные сведения см. в разделе [с помощью ключевого слова extern для задания компоновки](../cpp/using-extern-to-specify-linkage.md)

[/Zc: externconstexpr](../build/reference/zc-externconstexpr.md) компилятора предписывает компилятору для применения [внешнюю компоновку]() к переменным, объявленным с помощью `extern constexpr`. В более ранних версиях Visual Studio и по умолчанию или если **/Zc:externConstexpr-** указан, Visual Studio применяет внутреннюю компоновку для **constexpr** переменные, даже если **extern** используется ключевое слово. **/Zc: externconstexpr** параметр доступен, начиная с Visual Studio 2017 15.6 обновления. и по умолчанию отключены. / Zc: externconstexpr /permissive-option не включается.

В следующем коде показано два **extern** объявления, `DefinedElsewhere` (обозначает имя, определенное в другой записи преобразования) и `DefinedHere` (обозначает имя, определенное во внешней области видимости):

```cpp
// external.cpp
// DefinedElsewhere is defined in another translation unit
extern int DefinedElsewhere;   
int main() {
   int DefinedHere; 
   {
      // refers to DefinedHere in the enclosing scope
      extern int DefinedHere;
   }
}
```

## <a name="thread_local"></a> thread_local (C ++ 11)

Переменная, объявленная с описателем `thread_local`, доступна только в том потоке, в котором она была создана. Переменная создается при создании потока и уничтожается при его уничтожении. Каждый поток имеет свою собственную копию переменной. В Windows `thread_local` функционально эквивалентен системам Microsoft [__declspec (thread)](../cpp/thread.md) атрибута.

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

Следует помнить о `thread_local` описатель:

- Динамически инициализированных локальные переменные потока в библиотеках DLL не могут быть инициализированы правильно на всех вызывающих потоках. Дополнительные сведения см. [здесь](thread.md).

-  `thread_local` Описатель могут быть объединены с **статический** или **extern**.

-  Можно применить `thread_local` только к объявлениям и определениям; данных `thread_local` нельзя использовать в объявлениях или определениях функций.

-  `thread_local` можно задавать только для элементов данных со статической длительностью хранения. Сюда входят глобальные объекты данных (оба **статический** и **extern**), локальные статические объекты и статические данные-члены классов. Любой локальная переменная объявлена `thread_local` является неявно статическим, если предоставляется никакому другому классу хранения; другими словами, в области видимости блока `thread_local` эквивалентен `thread_local static`. 

-  `thread_local` следует использовать для объявления и определения локального объекта потока независимо от того, выполняются ли объявление и определение в одном файле или в отдельных файлах.

В Windows `thread_local` функционально эквивалентен [__declspec(thread)](../cpp/thread.md) за исключением того, что **__declspec(thread)** могут применяться в определение типа и является допустимым в коде C. По возможности следует использовать `thread_local`, поскольку он является частью стандарта C++ и поэтому обладает большей переносимостью.

##  <a name="register"></a>  Регистрация

**Visual Studio 2017 версии 15.3 и более поздние версии** (состав [/std: c ++ 17](../build/reference/std-specify-language-standard-version.md)): **зарегистрировать** ключевого слова больше не является поддерживаемым классом хранилища. Ключевое слово остается зарезервированным в стандарте для использования в будущем. 

```cpp
   register int val; // warning C5033: 'register' is no longer a supported storage class
```

## <a name="example-automatic-vs-static-initialization"></a>Пример: автоматический и статическая инициализация

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

В этом примере показано, как и когда объекты `I1`, `I2`, и `I3` инициализируются и время их удаления.

Существует несколько моментов, о программе:

- Во-первых, `I1` и `I2` автоматически удаляются, когда поток элемента управления выходит за пределы блока, в котором они определены.

- Во-вторых, в C++ не обязательно объявлять объекты или переменные в начале блока. Более того, эти объекты инициализируются, только если поток элемента управления достигает их определения. (Примерами таких определений являются `I2` и `I3`.) С помощью выходных данных можно точно определить время их инициализации.

- Наконец, статические локальные переменные, например `I3`, сохраняют свои значения длительности программы, но удаляются при завершении работы программы.

## <a name="see-also"></a>См. также
 [Объявления и определения](../cpp/declarations-and-definitions-cpp.md)