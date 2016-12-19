---
title: "Предупреждение компилятора (уровень 1) C4733 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4733"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4733"
ms.assetid: 7ef4f577-772d-4b66-a7bf-8958a6b250bc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4733
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Присваивание для "FS:0" во встроенном ассемблерном коде: обработчик не зарегистрирован как безопасный  
  
 Функция, изменяющая значение по адресу FS:0 для добавления нового обработчика исключений, может не работать с безопасными исключениями. Это может быть связано с тем, что обработчик не зарегистрирован как допустимый \(см. описание параметра [\/SAFESEH](../Topic/-SAFESEH%20\(Image%20has%20Safe%20Exception%20Handlers\).md)\).  
  
 Чтобы устранить это предупреждение, удалите определение FS:0 или отключите предупреждение и используйте параметр [.SAFESEH](../Topic/.SAFESEH.md) для определения обработчиков безопасных исключений.  
  
 Следующий пример приводит к возникновению ошибки C4733:  
  
```  
// C4733.cpp  
// compile with: /W1 /c  
// processor: x86  
#include "stdlib.h"  
#include "stdio.h"  
void my_handler()  
{  
   printf("Hello from my_handler\n");  
   exit(1);  
}  
  
int main()  
{  
   _asm {  
      push    my_handler  
      mov     eax, DWORD PTR fs:0  
      push    eax  
      mov     DWORD PTR fs:0, esp   // C4733  
   }  
  
   *(int*)0 = 0;  
}  
```