---
title: Операторы new и delete
description: Операторы new и DELETE языка C++ позволяют контролировать выделение памяти.
ms.date: 07/07/2020
helpviewer_keywords:
- new keyword [C++]
- delete keyword [C++]
ms.openlocfilehash: e609d1fdbd4f945ab8709c554d1396100027c4c1
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/08/2020
ms.locfileid: "86127844"
---
# <a name="new-and-delete-operators"></a>Операторы `new` и `delete`

C++ поддерживает динамическое выделение и освобождение объектов с помощью [`new`](new-operator-cpp.md) операторов и [`delete`](delete-operator-cpp.md) . Эти операторы выделяют память для объектов из пула, называемого свободным хранилищем. **`new`** Оператор вызывает специальную функцию [`operator new`](new-operator-cpp.md) , и **`delete`** оператор вызывает специальную функцию [`operator delete`](delete-operator-cpp.md) .

**`new`** Функция в стандартной библиотеке c++ поддерживает поведение, заданное в стандарте c++, что вызывает `std::bad_alloc` исключение в случае сбоя выделения памяти. Если вы по-прежнему хотите использовать не вызывающую версию **`new`** , свяжите программу с *`nothrownew.obj`* . Однако при компоновке с параметр *`nothrownew.obj`* по умолчанию **`operator new`** в стандартной библиотеке C++ больше не работает.

Список файлов библиотеки в библиотеке времени выполнения C и стандартной библиотеке C++ см. в разделе [функции библиотеки CRT](../c-runtime-library/crt-library-features.md).

## <a name="the-new-operator"></a><a id="new_operator"> </a> `new` Оператор

Компилятор преобразует инструкцию, такую как this, в вызов функции **`operator new`** :

```cpp
char *pch = new char[BUFFER_SIZE];
```

Если запрос имеет нулевые байты хранилища, функция **`operator new`** возвращает указатель на отдельный объект. То есть повторные вызовы **`operator new`** возвращают разные указатели. Если недостаточно памяти для запроса на выделение, **`operator new`** создает `std::bad_alloc` исключение. Или возвращает, **`nullptr`** Если вы связались с поддержкой без вызова **`operator new`** .

Можно написать подпрограммы, которая пытается освободить память и повторить выделение памяти. Дополнительные сведения см. на веб-сайте [`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md). Дополнительные сведения о схеме восстановления см. в разделе [Обработка нехватки памяти](#handling-insufficient-memory) .

**`operator new`** В следующей таблице описаны две области для функций.

### <a name="scope-for-operator-new-functions"></a>Область действия для `operator new` функций

| Оператор | Область |
|--|--|
| **`::operator new`** | Глобальный |
| *имя класса***`::operator new`** | Класс |

Первый аргумент для **`operator new`** должен иметь тип `size_t` , определенный в \<stddef.h> , а тип возвращаемого значения — Always **`void*`** .

Глобальная **`operator new`** функция вызывается, когда **`new`** оператор используется для выделения объектов встроенных типов, объектов типа класса, которые не содержат определяемых пользователем **`operator new`** функций, и массивов любого типа. Если **`new`** оператор используется для выделения объектов типа класса, в котором **`operator new`** определен объект, **`operator new`** вызывается этот класс.

**`operator new`** Функция, определенная для класса, является статической функцией-членом (которая не может быть виртуальной), которая скрывает глобальную **`operator new`** функцию для объектов этого типа класса. Рассмотрим случай, когда **`new`** используется для выделения и установки памяти для заданного значения:

```cpp
#include <malloc.h>
#include <memory.h>

class Blanks
{
public:
    Blanks(){}
    void *operator new( size_t stAllocateBlock, char chInit );
};
void *Blanks::operator new( size_t stAllocateBlock, char chInit )
{
    void *pvTemp = malloc( stAllocateBlock );
    if( pvTemp != 0 )
        memset( pvTemp, chInit, stAllocateBlock );
    return pvTemp;
}
// For discrete objects of type Blanks, the global operator new function
// is hidden. Therefore, the following code allocates an object of type
// Blanks and initializes it to 0xa5
int main()
{
   Blanks *a5 = new(0xa5) Blanks;
   return a5 != 0;
}
```

Аргумент, заданный в круглых скобках, **`new`** передается в `Blanks::operator new` качестве `chInit` аргумента. Однако глобальная **`operator new`** функция скрыта, что приводит к формированию ошибки следующим кодом:

```cpp
Blanks *SomeBlanks = new Blanks;
```

Компилятор поддерживает массив **`new`** и операторы-члены **`delete`** в объявлении класса. Пример:

```cpp
class MyClass
{
public:
   void * operator new[] (size_t)
   {
      return 0;
   }
   void   operator delete[] (void*)
   {
   }
};

int main()
{
   MyClass *pMyClass = new MyClass[5];
   delete [] pMyClass;
}
```

### <a name="handling-insufficient-memory"></a>Обработка нехватки памяти

Тестирование на неудачное выделение памяти можно выполнить, как показано ниже.

```cpp
#include <iostream>
using namespace std;
#define BIG_NUMBER 100000000
int main() {
   int *pI = new int[BIG_NUMBER];
   if( pI == 0x0 ) {
      cout << "Insufficient memory" << endl;
      return -1;
   }
}
```

Существует другой способ обработки запросов на выделение памяти, завершившихся сбоем. Напишите пользовательскую подсистему восстановления для решения такой ошибки, а затем зарегистрируйте функцию, вызвав [`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md) функцию времени выполнения.

## <a name="the-delete-operator"></a><a id="delete_operator"> </a> `delete` Оператор

Память, выделенная динамически с помощью **`new`** оператора, может быть освобождена с помощью **`delete`** оператора. Оператор delete вызывает **`operator delete`** функцию, которая освобождает память в доступном пуле. Использование **`delete`** оператора также приводит к вызову деструктора класса (если он существует).

Существует глобальная функция и функции уровня класса **`operator delete`** . **`operator delete`** Для данного класса может быть определена только одна функция. Если она определена, то она скрывает глобальную **`operator delete`** функцию. Глобальная **`operator delete`** функция всегда вызывается для массивов любого типа.

Глобальная **`operator delete`** функция. Для глобальных **`operator delete`** функций и членов класса существуют две формы **`operator delete`** :

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

Для данного класса может присутствовать только одна из двух предыдущих форм. Первая форма принимает один аргумент типа **`void *`** , который содержит указатель на объект, который необходимо освободить. Вторая форма, размер освобождения, принимает два аргумента: первый — указатель на блок памяти для освобождения, а второй — число байтов для освобождения. Тип возвращаемого значения обеих форм — **`void`** ( **`operator delete`** не может возвращать значение).

Цель второй формы — ускорить поиск нужной категории размера объекта для удаления. Эти сведения часто не хранятся рядом с самим выделением и, скорее всего, не кэшируются. Вторая форма полезна, когда **`operator delete`** функция из базового класса используется для удаления объекта производного класса.

**`operator delete`** Функция является статической, поэтому она не может быть виртуальной. **`operator delete`** Функция подчиняется контролю доступа, как описано в разделе [Управление доступом к членам](member-access-control-cpp.md).

В следующем примере показаны определяемые пользователем **`operator new`** функции и, **`operator delete`** предназначенные для записи в журнал выделений и освобождений памяти:

```cpp
#include <iostream>
using namespace std;

int fLogMemory = 0;      // Perform logging (0=no; nonzero=yes)?
int cBlocksAllocated = 0;  // Count of blocks allocated.

// User-defined operator new.
void *operator new( size_t stAllocateBlock ) {
   static int fInOpNew = 0;   // Guard flag.

   if ( fLogMemory && !fInOpNew ) {
      fInOpNew = 1;
      clog << "Memory block " << ++cBlocksAllocated
          << " allocated for " << stAllocateBlock
          << " bytes\n";
      fInOpNew = 0;
   }
   return malloc( stAllocateBlock );
}

// User-defined operator delete.
void operator delete( void *pvMem ) {
   static int fInOpDelete = 0;   // Guard flag.
   if ( fLogMemory && !fInOpDelete ) {
      fInOpDelete = 1;
      clog << "Memory block " << cBlocksAllocated--
          << " deallocated\n";
      fInOpDelete = 0;
   }

   free( pvMem );
}

int main( int argc, char *argv[] ) {
   fLogMemory = 1;   // Turn logging on
   if( argc > 1 )
      for( int i = 0; i < atoi( argv[1] ); ++i ) {
         char *pMem = new char[10];
         delete[] pMem;
      }
   fLogMemory = 0;  // Turn logging off.
   return cBlocksAllocated;
}
```

Приведенный выше код можно использовать для обнаружения "утечки памяти", то есть памяти, выделенной в бесплатном хранилище, но не освобожденной. Чтобы обнаружить утечки, глобальные **`new`** операторы и **`delete`** переопределяются для подсчета выделения и освобождения памяти.

Компилятор поддерживает массив **`new`** и операторы-члены **`delete`** в объявлении класса. Пример:

```cpp
// spec1_the_operator_delete_function2.cpp
// compile with: /c
class X  {
public:
   void * operator new[] (size_t) {
      return 0;
   }
   void operator delete[] (void*) {}
};

void f() {
   X *pX = new X[5];
   delete [] pX;
}
```
