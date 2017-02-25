---
title: "fenv_access | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.fenv_access"
  - "fenv_access_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fenv_access - прагма"
  - "прагмы, fenv_access"
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# fenv_access
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Отключает \(ON\) или включает \(OFF\) оптимизации, которые могут изменить проверки флагов и изменения режима.  
  
## Синтаксис  
  
```  
#pragma fenv_access [ON | OFF]  
```  
  
## Заметки  
 По умолчанию свойство `fenv_access` имеет значение OFF.  
  
 Дополнительные сведения о поведении чисел с плавающей запятой см. в разделе [\/fp \(Определение поведения с плавающей запятой\)](../build/reference/fp-specify-floating-point-behavior.md).  
  
 Ключевое слово `fenv_access` действует на следующие операции:  
  
-   Глобальное исключение общей части выражения  
  
-   Перемещение кода  
  
-   Свертка констант  
  
 Другие типы директив pragma для значений с плавающей запятой:  
  
-   [float\_control](../Topic/float_control.md)  
  
-   [fp\_contract](../preprocessor/fp-contract.md)  
  
## Пример  
  
```  
// pragma_directive_fenv_access_x86.cpp  
// compile with: /O2  
// processor: x86  
#include <stdio.h>  
#include <float.h>   
#include <errno.h>  
#pragma fenv_access (on)  
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
  **Вывод \= 9.999999776482582e\-003**   
## Пример  
 Следующий пример предназначен для компилятора, создающего выходные файлы для процессоров Itanium.  **\/fp:precise** сохраняет промежуточные результаты с расширенной точностью, при которой можно высчитывать значения больше FLT\_MAX \(3.402823466e\+38F\). В результате этого сумма будет иметь результат 1.0, как и при вычислении вручную.  **\/fp:strict** сохраняет промежуточные результаты с исходной точностью \(с плавающей запятой\), поэтому первое сложение дает результатом бесконечность, которое сохраняется на протяжении всего выражения.  
  
```  
// pragma_directive_fenv_access_IPF.cpp  
// compile with: /O2 /fp:precise  
// processor: IPF  
// compiling with /fp:precise prints 1.0F  
// compile with /fp:strict to print infinity  
  
#include <stdio.h>  
float arr[5] = {3.402823465e+38F,   
               3.402823462e+38F,  
               3.402823464e+38F,  
               3.402823463e+38F,  
               1.0F};  
  
int main() {  
   float sum = 0;  
   sum = arr[0] + arr[1] - arr[2] - arr[3] + arr[4];  
   printf_s("%f\n", sum);  
}  
```  
  
  **1.000000**   
## Пример  
 Закомментируем строку `#pragma fenv_access (on)` в первом примере. Обратите внимание на то, что вывод будет отличаться, поскольку компилятор выполняет оценку выражений во время компиляции, при котором не используется режим управления.  
  
```  
// pragma_directive_fenv_access_2.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>   
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
  **Вывод \= 1.000000000000000e\-002**   
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)