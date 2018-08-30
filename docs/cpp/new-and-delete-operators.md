---
title: новых и удаленных операторах | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a1470c544e624de4ef9fb570859dca9b282edde
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208070"
---
# <a name="new-and-delete-operators"></a>Операторы new и delete

C++ поддерживает динамическое выделение и освобождение памяти объектов с помощью [новый](../cpp/new-operator-cpp.md) и [удалить](../cpp/delete-operator-cpp.md) операторы. Эти операторы выделяют память для объектов из пула, называемого свободным хранилищем. **Новый** оператор вызывает специальную функцию [оператор new](../cpp/new-operator-cpp.md)и **удалить** оператор вызывает специальную функцию [оператор delete](../cpp/delete-operator-cpp.md).  
  
 **Новый** функции в стандартной библиотеке C++ поддерживает поведение, заданное в стандарте C++, которое заключается в случае сбоя выделения памяти исключение std::bad_alloc. Если вы хотите по-прежнему внеочередную версию **новый**, скомпонуйте программу с nothrownew.obj. Однако при компоновке с nothrownew.obj, значение по умолчанию **оператор new** в стандартной библиотеке C++ больше не функционирует.  
  
 Список библиотечных файлов, составляющих библиотеку времени выполнения C и стандартной библиотеки C++, см. в разделе [функций библиотеки CRT](../c-runtime-library/crt-library-features.md).  
  
##  <a id="new_operator"> </a> Оператор new  
 Если инструкцию, такую как следующие встречается в программе, он преобразует в вызов функции **оператор new**:  
  
```cpp  
char *pch = new char[BUFFER_SIZE];  
```  
  
Если запрос предназначен для нуля байтов памяти, **оператор new** возвращает указатель на конкретный объект (т. е. повторные вызовы **оператор new** возвращают разные указатели). Если недостаточно памяти для запроса на выделение **оператор new** создает исключение std::bad_alloc, или возвращает **nullptr** Если вы привязали в не создающие исключения **оператор new** поддержки.  
  
Можно написать подпрограмму, которая пытается освободить память и повторить попытку выделения; см. в разделе [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) Дополнительные сведения. Дополнительные сведения о схеме восстановления см. в разделе нехватки памяти обработка этого раздела.  

  
Две области для **оператор new** функции описаны в следующей таблице.  
  
### <a name="scope-for-operator-new-functions"></a>Области для функций operator new  
  
|Оператор|Область|  
|--------------|-----------|  
|**:: оператор new**|Global|  
|*Имя класса* **:: оператор new**|Класс|  
  
 Первый аргумент **оператор new** должен иметь тип `size_t` (типа, определенного в \<stddef.h >), и тип возвращаемого значения всегда **void** <strong>\*</strong>.  
  
 Глобальный **оператор new** функция вызывается, когда **новый** оператор используется для выделения объектов встроенных типов, объектов типа класса, не содержащих определяемых пользователем **оператор new** функций и массивов любого типа. При **новый** оператор используется для выделения объектов типа класса где **оператор new** определен, этот класс **оператор new** вызывается.  
  
 **Оператор new** функцию, определенную для класса, является статической функции-члене (которая таким образом, не может быть виртуальной), скрывающей глобальную **оператор new** функции для объектов этого типа класса. Рассмотрим случай, где **новый** используется для выделения памяти и установки конкретное значение:  
  
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
  
 Аргумент, предоставленный в круглые скобки, чтобы **новый** передается `Blanks::operator new` как `chInit` аргумент. Тем не менее глобальный **оператор new** функция скрыта, вызывая следующий код приводит к ошибке:  
  
```cpp  
Blanks *SomeBlanks = new Blanks;  
```  
  
 В Visual C++ 5.0 и более ранних версиях неклассовые типы и все массивы (независимо от того, были ли они типа **класс** типа) с использованием **новый** оператор всегда использовали глобальную **оператор new** функции.  
  
 Начиная с Visual C++ 5.0, компилятор поддерживает участников массива **новый** и **удалить** операторы в объявлении класса. Пример:  
  
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
  
 Есть другой способ обработки запросов на выделение памяти неудачных: написать процедуру настраиваемого восстановления для обработки такой ошибки, а затем зарегистрировать ее, вызвав [_set_new_handler](../c-runtime-library/reference/set-new-handler.md) функции времени выполнения.  
  
##  <a id="delete_operator"> </a> Оператор delete  
 Память, выделенную динамически с помощью **новый** оператор может освобождаться с помощью **удалить** оператор. Оператор delete вызывает **оператор delete** функцию, которая освобождает память в пул доступных. С помощью **удалить** оператор также вызывает деструктор класса (если таковой имеется) для вызова.  
  
 Существуют глобального уровня класса и **оператор delete** функции. Только один **оператор delete** функция может быть определена для данного класса; Если определен, он скрывает глобальное **оператор delete** функции. Глобальный **оператор delete** функция всегда вызывается для массивов любого типа.  
  
 Глобальный **оператор delete** функции. Предусмотрены две формы глобальный **оператор delete** и членов класса **оператор delete** функции:  
  
```cpp  
void operator delete( void * );  
void operator delete( void *, size_t );  
```  
  
 Для данного класса может присутствовать только один из перечисленных выше двух видов. Первая форма принимает один аргумент типа `void *`, который содержит указатель на освобождаемый объект. Вторая форма — освобождение с указанием размера — принимает два аргумента, первый из которых является указатель на освобождаемый блок памяти, а вторым — число освобождаемых байтов. Тип возвращаемого значения обе формы — **void** (**оператор delete** не может вернуть значение).  
  
 Вторая форма цель состоит в том, чтобы ускорить поиск правильного размера категорию объект для удаления, который часто не хранятся рядом выделение самого и скорее всего без кэширования; Вторая форма особенно полезна при **оператор delete** функция от базового класса используется для удаления объекта производного класса.  
  
 **Оператор delete** функция является статической, поэтому не может быть виртуальной. **Оператор delete** функция подчиняется контроля доступа, как описано в разделе [управления доступом к членам](../cpp/member-access-control-cpp.md).  
  
 В следующем примере показано, определяемые пользователем **оператор new** и **оператор delete** функции, предназначенные для записи в журнал операций выделения и освобождения памяти:  
  
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
  
 Начиная с Visual C++ 5.0, компилятор поддерживает участников массива **новый** и **удалить** операторы в объявлении класса. Пример:  
  
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