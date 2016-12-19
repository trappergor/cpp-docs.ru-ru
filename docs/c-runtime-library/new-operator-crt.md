---
title: "оператор new (CRT) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "new[]"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "оператор new[]"
  - "вектор new"
ms.assetid: 79682f85-6889-40f6-b8f7-9eed5176ea35
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# оператор new (CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Выделяет блок памяти из кучи.  
  
## Синтаксис  
  
```  
  
      void *__cdecl operator new[](size_t count);  
void *__cdecl operator new[] (  
   size_t count,   
   void * object  
) throw();  
void *__cdecl operator new[] (  
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
 Эта форма `operator new` известна как векторная форма new, в отличие от скалярной формы new \([оператор new](../c-runtime-library/operator-new-crt.md)\).  
  
 Первая форма данного оператора известна как неразмещающая форма.  Вторая форма данного оператора известна как размещающая форма, а третья форма данного оператора — не генерирующая исключения размещающая форма.  
  
 Первая форма оператора определяется компилятором и не требует включения new.h в программу.  
  
 [оператор delete&#91;&#93;](../Topic/operator%20delete\(%3Cnew%3E\).md) освобождает память, выделенную с помощью оператора new.  
  
 Можно настроить, возвращает ли оператор `operator new[]` значение NULL или создает исключение при сбое.  Дополнительные сведения см. в разделе [Операторы new и delete](../cpp/new-and-delete-operators.md).  
  
 За исключением возможности разрешить или запретить генерацию исключений, CRT `operator new` работает подобно [оператору new&#91;&#93;](../Topic/operator%20new\(%3Cnew%3E\).md) в стандартной библиотеке C\+\+.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`new[]`|\<new.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../c-runtime-library/compatibility.md) во введении.  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../c-runtime-library/crt-library-features.md).  
  
## Пример  
 Далее показано, как использовать векторную неразмещающую форму `operator new`.  
  
```  
// crt_new4.cpp  
#include <stdio.h>  
int main() {  
   int * k = new int[10];  
   k[0] = 21;  
   printf("%d\n", k[0]);  
   delete [] k;  
}  
```  
  
 Далее показано, как использовать векторную размещающую форму `operator new`.  
  
```  
// crt_new5.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * i = new int[10];  
   i[0] = 21;  
   printf("%d\n", i[0]);  
   // initialize existing memory (i) with, in this case, int[[10]  
   int * j = new(i) int[10];   // placement vector new  
   printf("%d\n", j[0]);  
   j[0] = 22;  
   printf("%d\n", i[0]);  
   delete [] i;   // or, could have deleted [] j   
}  
```  
  
 Далее показано, как использовать векторную размещающую не генерирующую исключения форму `operator new`.  
  
```  
// crt_new6.cpp  
#include <stdio.h>  
#include <new.h>  
int main() {  
   int * k = new(std::nothrow) int[10];  
   k[0] = 21;  
   printf("%d\n", k[0]);  
   delete [] k;  
}  
```  
  
## См. также  
 [Выделение памяти](../c-runtime-library/memory-allocation.md)