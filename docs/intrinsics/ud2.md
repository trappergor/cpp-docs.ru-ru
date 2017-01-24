---
title: "__ud2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__ud2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Инструкция UD2"
  - "Встроенная функция __ud2"
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
caps.latest.revision: 7
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __ud2
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Только для систем Microsoft**  
  
 Вызывает неопределенную инструкцию.  
  
## Синтаксис  
  
```  
void __ud2();  
```  
  
## Заметки  
 Процессор вызывает недопустимое исключение при выполнении операций является неопределенной инструкция.  
  
 Функция `__ud2` эквивалентна инструкцие на компьютере `UD2` и доступна только в режиме ядра.  Дополнительные сведения см. в документе «руководство разработчика программного обеспечения архитектуры Intel, данном 2. Справочник по наборам инструкций,» на [Intel Корпорация](http://go.microsoft.com/fwlink/?LinkId=127) сайте.  
  
## Требования  
  
|Встроенный объект|Архитектура|  
|-----------------------|-----------------|  
|`__ud2`|x86, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h\>  
  
## ЭЛЕМЕНТ, относящийся Майкрософт  
  
## Пример  
 В следующем примере выполняется неопределенная инструкция, которая вызывает исключение.  Обработчик исключений затем код возврата от нуля до одного.  
  
```  
// __ud2_intrinsic.cpp  
#include <stdio.h>  
#include <intrin.h>  
#include <excpt.h>  
// compile with /EHa  
  
int main() {  
  
// Initialize the return code to 0.  
 int ret = 0;  
  
// Attempt to execute an undefined instruction.  
  printf("Before __ud2(). Return code = %d.\n", ret);  
  __try {   
  __ud2();   
  }  
  
// Catch any exceptions and set the return code to 1.  
  __except(EXCEPTION_EXECUTE_HANDLER){  
  printf("  In the exception handler.\n");  
  ret = 1;  
  }  
  
// Report the value of the return code.   
  printf("After __ud2().  Return code = %d.\n", ret);  
  return ret;  
}  
```  
  
  **Перед \_\_ud2 \(\).**  
 **Код возврата \= 0.**  
 **в обработчике исключений.**  
 **После \_\_ud2 \(\).**  
 **Код возврата \= 1.**   
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)