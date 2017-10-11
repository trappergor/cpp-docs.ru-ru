---
title: "новые и удалить операторы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- delete_cpp
- new
dev_langs:
- C++
helpviewer_keywords:
- new keyword [C++], dynamic allocation of objects
- nothrownew.obj
- delete keyword [C++], syntax
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 88f91e113ef47dc44ec0a300a99051cfaed3f08c
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="new-and-delete-operators"></a>Операторы new и delete

C++ поддерживает динамическое выделение и освобождение памяти объектов с помощью [новый](../cpp/new-operator-cpp.md) и [удалить](../cpp/delete-operator-cpp.md) операторы. Эти операторы выделяют память для объектов из пула, называемого свободным хранилищем. `new` Оператор вызывает специальную функцию [оператор new](../cpp/new-operator-cpp.md)и `delete` оператор вызывает специальную функцию [оператор delete](../cpp/delete-operator-cpp.md).  
  
 В Visual C++ .NET 2002 `new` функции в стандартной библиотеке C++ будет поддерживать поведение, заданное в стандарте C++, то есть исключение std::bad_alloc в случае сбоя выделения памяти. Если по-прежнему требуется версия не создающие `new`, скомпонуйте программу с nothrownew.obj. Однако при компоновке с nothrownew.obj, значение по умолчанию `operator new` в стандартной библиотеке C++ больше не функционирует.  
  
 Список библиотечных файлов, составляющих библиотеку времени выполнения C и в стандартной библиотеке C++ см. в разделе [возможности библиотеки CRT](../c-runtime-library/crt-library-features.md).  
  
##  <a id="new_operator"></a> Оператор new  
 При обнаружении в программе оператора, подобного показанному ниже, он преобразуется в вызов функции `operator new`.  
  
```cpp  
char *pch = new char[BUFFER_SIZE];  
```  
  
Если в запросе требуется нуль байтов памяти, **оператор new** возвращает указатель на отдельный объект (т. е. повторные вызовы **оператор new** возвращают разные указатели). Если недостаточно памяти для запроса на выделение **оператор new** создает исключение std::bad_alloc или возвращает **nullptr** Если вы привязали в не создающие `operator new` поддержки.  
  
Можно написать процедуру, которая пытается освободить память и повторить попытку выделения; в разделе [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) для получения дополнительной информации. Дополнительные сведения о схеме восстановления см. в разделе нехватки памяти обработка части этого раздела.  

  
В следующей таблице описаны две области для функций `operator new`.  
  
### <a name="scope-for-operator-new-functions"></a>Области для функций operator new  
  
|Оператор|Область|  
|--------------|-----------|  
|**:: оператор new**|Global|  
|*Имя класса* **:: оператор new**|Класс|  
  
 Первый аргумент **оператор new** должен иметь тип **size_t** (тип, определенный в STDDEF. H), а тип возвращаемого значения — всегда **void \* **.  
  
 Глобальный **оператор new** функция вызывается, когда **новый** оператор, используемый для выделения объектов встроенных типов, определяемые пользователем объекты типа класса, которые не содержат **оператор new** функций и массивов любого типа. При **новый** оператор, используемый для выделения объектов типа класса где **оператор new** определен, этот класс **оператор new** вызывается.  
  
 **Оператор new** функция, определенная для класса, является статической функцией-членом (которая таким образом, не могут быть виртуальными), скрывающей глобальную **оператор new** функция для объектов этого типа класса. Рассмотрим случай, когда **новый** используется для выделения памяти и установки заданное значение:  
  
```cpp  
// spec1_the_operator_new_function1.cpp  
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
  
 Аргумент, предоставленный в круглые скобки, чтобы **новый** передается `Blanks::operator new` как `chInit` аргумент. Однако глобальная **оператор new** функция скрыта, вызывая следующего кода приводит к ошибке:  
  
```cpp  
Blanks *SomeBlanks = new Blanks;  
```  
  
 В Visual C++ 5.0 и более ранних версиях неклассовые типы и все массивы (независимо от того, были ли они типа **класса** типа) выделенного с помощью **новый** оператор всегда использовали глобальную **оператор new** функции.  
  
 Начиная с Visual C++ 5.0, компилятор поддерживает члена массива **новый** и **удалить** операторы в объявлении класса. Пример:  
  
```cpp  
// spec1_the_operator_new_function2.cpp  
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
 Проверку сбоев при выделении памяти можно выполнять при помощи кода из следующего примера:  
  
```cpp  
// insufficient_memory_conditions.cpp  
// compile with: /EHsc  
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
  
 Есть другой способ обработки сбоев при выделении памяти: написать собственную процедуру восстановления для обработки такой сбой, а затем зарегистрировать ее, вызвав [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) функции времени выполнения.  
  
##  <a id="delete_operator"></a> Оператор delete  
 Память, выделенную динамически с помощью **новый** оператор может быть освобожден с помощью **удалить** оператор. Оператор delete вызывает **оператор delete** функции, которая освобождает память в пул доступных. С помощью **удалить** оператор также вызывается деструктор класса (если есть) для вызова.  
  
 Глобальные и области видимости класса **оператор delete** функции. Только один **оператор delete** функции могут быть определены для данного класса, если определено, он скрывает глобальное **оператор delete** функции. Глобальный **оператор delete** функция всегда вызывается для массивов любого типа.  
  
 Глобальный **оператор delete** функции. Существует две формы для глобального **оператор delete** и член класса **оператор delete** функции:  
  
```cpp  
void operator delete( void * );  
void operator delete( void *, size_t );  
```  
  
 Для данного класса может присутствовать только один из двух форм выше. Первая форма принимает один аргумент типа **void \* **, который содержит указатель на освобождаемый объект. Вторая форма — изъятие с ограниченным размером — принимает два аргумента, первый из которых является указатель на освобождаемый блок памяти, а вторым — число освобождаемых байтов. Тип возвращаемого значения обе формы `void` (**оператор delete** не может вернуть значение).  
  
 Вторая форма призван ускорить поиск категории правильный размер объекта, которые требуется удалить, который часто не хранятся рядом выделение самого и скорее всего некэшированных; Вторая форма особенно полезна при **оператор delete** функции из базового класса используется для удаления объекта производного класса.  
  
 **Оператор delete** функция является статической, поэтому не может быть виртуальным. `operator delete` Функции подчиняется правилам управления доступом, как описано в [управления доступом к членам](../cpp/member-access-control-cpp.md).  
  
 В следующем примере показано, определяемых пользователем **оператор new** и **оператор delete** функций, предназначенных для ведения журнала выделения и освобождения памяти:  
  
```cpp  
// spec1_the_operator_delete_function1.cpp  
// compile with: /EHsc  
// arguments: 3  
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
  
 Представленный выше код можно использовать для обнаружения "утечек памяти", т. е. памяти, которая выделяется в свободном хранилище, но никогда не освобождается. Для выполнения такого обнаружения глобальные **новый** и **удалить** операторы переопределяются для учета выделения и освобождения памяти.  
  
 Начиная с Visual C++ 5.0, компилятор поддерживает члена массива **новый** и **удалить** операторы в объявлении класса. Пример:  
  
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


