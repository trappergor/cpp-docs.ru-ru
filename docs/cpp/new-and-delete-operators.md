---
title: Операторы new и delete
ms.date: 11/19/2019
helpviewer_keywords:
- new keyword [C++]
- delete keyword [C++]
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
ms.openlocfilehash: 2fd665ce2570bbe7750684057cdf7f517f6f64f3
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445456"
---
# <a name="new-and-delete-operators"></a>Операторы new и delete

C++поддерживает динамическое выделение и освобождение объектов с помощью операторов [New](new-operator-cpp.md) и [Delete](delete-operator-cpp.md) . Эти операторы выделяют память для объектов из пула, называемого свободным хранилищем. **Новый** оператор вызывает Специальный [оператор функции New](new-operator-cpp.md), а оператор **Delete** вызывает Специальный [оператор функции Delete](delete-operator-cpp.md).

**Новая** функция в C++ стандартной библиотеке поддерживает поведение, заданное в C++ стандарте, что вызывает исключение std:: bad_alloc, если выделение памяти завершается ошибкой. Если вы по-прежнему хотите использовать **несоздаваемую версию, свяжите**программу с носровнев. obj. Однако при компоновке с помощью носровнев. obj оператор по умолчанию **New** в C++ стандартной библиотеке больше не работает.

Список файлов библиотеки, составляющих библиотеку времени выполнения C и C++ стандартную библиотеку, см. в разделе [функции библиотеки CRT](../c-runtime-library/crt-library-features.md).

##  <a id="new_operator"> </a> Оператор New

При обнаружении в программе оператора, следующего как приведенный ниже, он преобразуется в вызов **оператора функции New**:

```cpp
char *pch = new char[BUFFER_SIZE];
```

Если запрос имеет нулевые байты хранилища, **оператор New** возвращает указатель на отдельный объект (то есть повторные вызовы **оператора New** возвращают разные указатели). Если недостаточно памяти для запроса на выделение, **оператор New** выдает исключение `std::bad_alloc` или возвращает **nullptr** , если у вас есть ссылка в **новой поддержке оператора** без вызова.

Вы можете написать подпрограммы, которая пытается освободить память и повторить выделение памяти. Дополнительные сведения см. в разделе [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) . Дополнительные сведения о схеме восстановления см. в разделе Обработка нехватки памяти этой статьи.

В следующей таблице описаны две области действия **новых функций operator** .

### <a name="scope-for-operator-new-functions"></a>Область действия новых функций оператора

|Оператор|Область|
|--------------|-----------|
|**:: оператор New**|Global|
|*Class-Name* **:: оператор New**|Class|

Первый аргумент **оператора New** должен иметь тип `size_t` (тип, определенный в \<STDDEF. h >), а тип возвращаемого значения всегда имеет **значение void** <strong>\*</strong>.

Глобальная функция **New** вызывается, когда оператор **New** используется для выделения объектов встроенных типов, объектов типа класса, которые не содержат определяемых пользователем **операторов New** и массивов любого типа. Если оператор **New** используется для выделения объектов типа класса, в котором определен **оператор New** , вызывается **оператор New** этого класса.

Новая функция- **оператор** , определенная для класса, — это статическая функция-член (которая не может, следовательно, быть виртуальной), которая скрывает глобальную функцию **New** для объектов этого типа класса. Рассмотрим случай, когда **New** используется для выделения и установки памяти для заданного значения:

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

Аргумент, заданный в круглых скобках для **New** , передается в `Blanks::operator new` в качестве аргумента `chInit`. Тем не менее функция глобального **оператора New** скрыта, что приводит к формированию ошибки следующим кодом:

```cpp
Blanks *SomeBlanks = new Blanks;
```

Компилятор поддерживает операторы **New** и **Delete** массива членов в объявлении класса. Пример:

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

Существует другой способ обработки запросов на выделение памяти, завершившихся сбоем. Напишите пользовательскую подсистему восстановления для решения такой ошибки, а затем зарегистрируйте функцию, вызвав функцию [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) времени выполнения.

##  <a id="delete_operator"> </a> Оператор DELETE

Память, выделенная динамически с помощью оператора **New** , можно освободить с помощью оператора **Delete** . Оператор delete вызывает функцию **operator delete** , которая освобождает память в доступном пуле. Использование оператора **Delete** также приводит к вызову деструктора класса (если он есть).

Существуют глобальные функции и **операторы удаления** с областью действия класса. Для данного класса может быть определена только одна функция **Delete оператора** . Если этот параметр определен, функция **Delete оператора** Global может быть скрыта. Функция глобального **оператора delete** всегда вызывается для массивов любого типа.

Функция **Delete оператора** Global. Для функций глобального **оператора delete** и **оператора** -члена класса существуют две формы:

```cpp
void operator delete( void * );
void operator delete( void *, size_t );
```

Для данного класса может присутствовать только одна из двух предыдущих форм. Первая форма принимает один аргумент типа `void *`, который содержит указатель на объект, который необходимо освободить. Вторая форма: освобождение размера — принимает два аргумента, первый из которых является указателем на блок памяти для освобождения, а второй — число байтов для освобождения. Тип возвращаемого значения обеих форм — **void** (**оператор DELETE** не может возвращать значение).

Цель второй формы — ускорить поиск нужной категории размера удаляемого объекта, который часто не хранится рядом с самим выделением и, вероятно, некэшированным. Вторая форма полезна, если функция **Delete оператора** из базового класса используется для удаления объекта производного класса.

Функция **Delete оператора** является статической; Поэтому он не может быть виртуальным. Функция **Delete оператора** подчиняется контролю доступа, как описано в разделе [Управление доступом к членам](member-access-control-cpp.md).

В следующем примере показаны определяемые пользователем **операторы new** и Function **Delete** , предназначенные для записи в журнал выделений и освобождений памяти.

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

Представленный выше код можно использовать для обнаружения "утечек памяти", т. е. памяти, которая выделяется в свободном хранилище, но никогда не освобождается. Для выполнения этого обнаружения глобальные операторы **New** и **Delete** переопределяются для подсчета выделения и освобождения памяти.

Компилятор поддерживает операторы **New** и **Delete** массива членов в объявлении класса. Пример:

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
