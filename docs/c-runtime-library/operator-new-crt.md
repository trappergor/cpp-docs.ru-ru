---
title: "оператор new (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr90.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "оператор new"
  - "скалярное новое"
ms.assetid: 4ae51618-a4e6-4172-b324-b99d86d1bdca
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# оператор new (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выделяет блок памяти из кучи.  
  
## Синтаксис  
  
```  
  
      void *__cdecl operator new(  
   size_t count  
);  
void *__cdecl operator new(  
   size_t count,   
   void * object  
) throw();  
void *__cdecl operator new(  
   size_t count,   
   const std::nothrow_t&  
) throw();  
```  
  
#### Параметры  
 *count*  
 Размер выделяемой памяти.  
  
 *object*  
 Указатель на блок памяти, в котором будет создан объект.  
  
## Возвращаемое значение  
 Указатель на наименьший байтовый адрес вновь выделенного хранилища.  
  
## Заметки  
 Эта форма `operator new` известна как скалярная форма new, в отличие от векторной формы new \([оператор new&#91;&#93;](../c-runtime-library/new-operator-crt.md)\).  
  
 Первая форма данного оператора известна как неразмещающая форма.  Вторая форма данного оператора известна как размещающая форма, а третья форма данного оператора — не генерирующая исключения размещающая форма.  
  
 Первая форма оператора определяется компилятором и не требует включения new.h в программу.  
  
 [оператор delete](../c-runtime-library/operator-delete-crt.md) освобождает память, выделенную `operator new`.  
  
 Можно настроить, возвращает ли оператор new значение NULL или создает исключение при сбое.  Дополнительные сведения см. в разделе [Операторы new и delete](../cpp/new-and-delete-operators.md).  
  
 За исключением возможности разрешить или запретить генерацию исключений, CRT `operator new` работает подобно [оператору new](../Topic/operator%20new%20\(%3Cnew%3E\).md) в стандартной библиотеке C\+\+.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|**new**|\<new.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../c-runtime-library/crt-library-features.md).  
  
## Пример  
 Далее показано, как использовать скалярную неразмещающую форму `operator new`.  
  
```  
// crt_new1.cpp  
#include <stdio.h>  
int main() {  
   int * i = new int(6);  
   printf("%d\n", *i);  
   delete i;  
}  
```  
  
 Далее показано, как использовать скалярную размещающую форму `operator new`.  
  
```  
// crt_new2.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * i = new int(12);  
   printf("*i = %d\n", *i);  
   // initialize existing memory (i) with, in this case, int(7)  
   int * j = new(i) int(7);   // placement new  
   printf("*j = %d\n", *j);  
   printf("*i = %d\n", *i);  
   delete i;   // or, could have deleted j  
}  
```  
  
 Далее показано, как использовать скалярную размещающую не генерирующую исключения форму `operator new`.  
  
```  
// crt_new3.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   // allocates memory, initialize (8) and if call fails, new returns null  
   int * k = new(std::nothrow) int(8);   // placement new  
   printf("%d\n", *k);  
   delete k;  
}  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Выделение памяти](../c-runtime-library/memory-allocation.md)