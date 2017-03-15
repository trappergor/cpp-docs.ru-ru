---
title: "Операторы new и delete | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "delete_cpp"
  - "new_cpp"
  - "new"
  - "delete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delete - ключевое слово [C++], синтаксис"
  - "new - ключевое слово [C++], динамическое выделение объектов"
  - "nothrownew.obj"
ms.assetid: fa721b9e-0374-4f04-bb87-032ea775bcc8
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Операторы new и delete
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ поддерживает динамическое выделение и освобождение памяти объектов с использованием операторов [new](../cpp/new-operator-cpp.md) и [delete](../cpp/delete-operator-cpp.md).  Эти операторы выделяют память для объектов из пула, называемого свободным хранилищем.  Оператор `new` вызывает специальную функцию [operator new](../misc/operator-new-function.md), а оператор `delete` вызывает специальную функцию [operator delete](../Topic/operator%20delete%20Function.md).  
  
 В [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] .NET 2002 функция `new` из стандартной библиотеки C\+\+ поддерживает поведение, определенное в стандарте C\+\+, то есть создает исключение std::bad\_alloc в случае сбоя при выделении памяти.  
  
 Функция `new` библиотеки времени выполнения C также создает исключение std::bad\_alloc в случае сбоя выделения памяти.  
  
 Если для библиотеки времени выполнения C требуется использовать версию функции `new`, не вызывающую исключения, скомпонуйте программу с nothrownew.obj.  Однако при компоновке с nothrownew.obj функция `new` из стандартной библиотеки C\+\+ работать не будет.  
  
 Список библиотечных файлов, входящий в библиотеку времени выполнения C и стандартную библиотеку C\+\+, см. в статье [Особенности библиотеки CRT](../c-runtime-library/crt-library-features.md).  
  
## Оператор new  
 При обнаружении в программе оператора, подобного показанному ниже, он преобразуется в вызов функции `operator new`.  
  
```  
char *pch = new char[BUFFER_SIZE];  
```  
  
 Если в запросе требуется нуль байтов памяти, функция **operator new** возвращает указатель на отдельный объект \(т. е. повторные вызовы **operator new** возвращают разные указатели\).  Если возникает нехватка памяти для выполнения запроса на выделение, функция **operator new** возвращает значение **NULL** или создает исключение. \(Дополнительные сведения см. в статье [Операторы new и delete](../cpp/new-and-delete-operators.md).\)  
  
 Можно написать процедуру, которая будет пытаться освободить память и повторить попытку выделения; дополнительные сведения см. в разделе [\_set\_new\_handler](../Topic/_set_new_handler.md).  Более подробные сведения о схеме восстановления см. в разделе [Обработка в случаях нехватки памяти](../Topic/Handling%20Insufficient%20Memory%20Conditions.md).  
  
 В следующей таблице описаны две области для функций `operator new`.  
  
### Области для функций operator new  
  
|Оператор|Область|  
|--------------|-------------|  
|**::operator new**|Глобальные|  
|*имя\-класса* **::operator new**|Класс|  
  
 Первый аргумент функции **operator new** должен иметь тип **size\_t** \(определенный в файле STDDEF.H\), а тип возвращаемых данных — всегда **void \***.  
  
 Глобальная функция **operator new** вызывается при использовании оператора **new** для выделения объектов встроенных типов, объектов типа класса \(не содержащих определяемых пользователем функций **operator new**\) и массивов любого типа.  Если оператор **new** используется для выделения объектов типа класса, где определена функция **operator new**, вызывается функция **operator new** этого класса.  
  
 Функция **operator new**, определенная для класса, является статической функцией\-членом \(которая, следовательно, не может быть виртуальной\), скрывающей глобальную функцию **operator new** для объектов этого типа класса.  Рассмотрим случай использования **new** для выделения памяти и установки для нее заданного значения.  
  
```  
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
  
 Аргумент, указанный для **new** в скобках, передается в `Blanks::operator new` в качестве аргумента `chInit`.  Однако глобальная функция **operator new** скрыта, из\-за чего код \(такой, как показан ниже\) приводит к ошибке.  
  
```  
Blanks *SomeBlanks = new Blanks;  
```  
  
 В Visual C\+\+ 5.0 и более ранних версиях неклассовые типы и все массивы, выделенные с помощью оператора **new**, всегда использовали глобальную функцию **operator new** \(независимо от того, были ли они типа **class**\).  
  
 Начиная с Visual C\+\+ 5.0, компилятор поддерживает в объявлении класса операторы **new** и **delete** массива членов.  Пример:  
  
```  
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
  
### Обработка нехватки памяти  
 Проверку сбоев при выделении памяти можно выполнять при помощи кода из следующего примера:  
  
```  
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
  
 Существует и другой способ обработки сбоев при выделении памяти: вы можете написать собственную процедуру восстановления, которая будет их обрабатывать, а затем зарегистрировать ее, вызвав функцию времени выполнения [\_set\_new\_handler](../Topic/_set_new_handler.md).  
  
## Оператор delete  
 Память, выделенную динамически с помощью оператора **new**, можно освободить с помощью оператора **delete**.  Оператор delete вызывает функцию **operator delete**, которая освобождает память, возвращая ее в пул доступной памяти.  При использовании оператора **delete** также вызывается деструктор класса \(при его наличии\).  
  
 Имеются функции **operator delete** глобального уровня и области определения класса.  Для конкретного класса можно определить только одну функцию **operator delete**. Если она определена, глобальная функция **operator delete** будет скрыта.  Глобальная функция **operator delete** всегда вызывается для массивов любого типа.  
  
 Глобальная функция **operator delete** \(если она объявлена\) принимает один аргумент типа **void \***, который содержит указатель на освобождаемый объект.  Тип возвращаемого значения — `void` \(**operator delete** не может вернуть значение\).  Для функций **operator delete** члена класса предусмотрены две формы:  
  
```  
void operator delete( void * );  
void operator delete( void *, size_t );  
```  
  
 Для данного класса может присутствовать только один из указанных выше вариантов.  Первая форма работает согласно описанию для глобальной функции `operator delete`.  Вторая форма принимает два аргумента, первым из которых является указатель на освобождаемый блок памяти, а вторым — число освобождаемых байтов.  Вторая форма особенно полезна при использовании функции **operator delete** из базового класса для удаления объекта производного класса.  
  
 Функция **operator delete** является статической, поэтому она не может быть виртуальной.  Функция `operator delete` подчиняется правилам управления доступом, как описано в разделе [Управление доступом к членам](../cpp/member-access-control-cpp.md).  
  
 В следующем примере показаны определенные пользователем функции **operator new** и **operator delete**, предназначенные для записи операций выделения и освобождения памяти в журнал.  
  
```  
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
  
 Представленный выше код можно использовать для обнаружения "утечек памяти", т. е. памяти, которая выделяется в свободном хранилище, но никогда не освобождается.  Для выполнения такого обнаружения глобальные операторы **new** и **delete** переопределяются для учета выделения и освобождения памяти.  
  
 Начиная с Visual C\+\+ 5.0, компилятор поддерживает в объявлении класса операторы **new** и **delete** массива членов.  Пример:  
  
```  
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
  
## См. также  
 [Специальные функции\-члены](../misc/special-member-functions-cpp.md)