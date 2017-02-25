---
title: "Правила и ограничения при использовании функций Naked | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "функции naked"
ms.assetid: ff203858-2dd3-4a76-8a57-d0d06817adef
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Правила и ограничения при использовании функций Naked
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Microsoft  
 Для функций с атрибутом naked действуют следующие правила и ограничения:  
  
-   Оператор `return` не допускается.  
  
-   Конструкции структурированной обработки исключений и обработки исключений C\+\+ не допускаются, потому что они должны выполнять очистку в кадре стека.  
  
-   По этой же причине запрещена любая форма `setjmp`.  
  
-   Использование функции `_alloca` запрещено.  
  
-   Чтобы перед последовательностью пролога гарантировано не было никакого кода инициализации локальных переменных, инициализируемые локальные переменные в области функции не допускаются.  В частности, в области функции не допускается объявление объектов C\+\+.  Однако допускаются инициализируемые данные во вложенной области.  
  
-   Оптимизация указателя кадра \(параметр компилятора \/Oy\) не рекомендуется, но для функций с атрибутом naked она автоматически подавляется.  
  
-   Не допускается объявление объектов класса C\+\+ в лексической области функции.  Однако можно объявлять объекты во вложенном блоке.  
  
-   При компилировании с параметром [\/clr](../build/reference/clr-common-language-runtime-compilation.md) ключевое слово `naked` игнорируется.  
  
-   В случае функций с атрибутами naked и [\_\_fastcall](../cpp/fastcall.md) при наличии в коде C или C\+\+ ссылки на один из регистровых аргументов код пролога должен сохранять значения этого регистра в расположении стека для этой переменной.  Например:  
  
```  
// nkdfastcl.cpp  
// compile with: /c  
// processor: x86  
__declspec(naked) int __fastcall  power(int i, int j) {  
   // calculates i^j, assumes that j >= 0  
  
   // prolog  
   __asm {  
      push ebp  
      mov ebp, esp  
      sub esp, __LOCAL_SIZE  
     // store ECX and EDX into stack locations allocated for i and j  
     mov i, ecx  
     mov j, edx  
   }  
  
   {  
      int k = 1;   // return value  
      while (j-- > 0)   
         k *= i;  
      __asm {   
         mov eax, k   
      };  
   }  
  
   // epilog  
   __asm {  
      mov esp, ebp  
      pop ebp  
      ret  
   }  
}  
```  
  
## Завершение блока, относящегося только к системам Microsoft  
  
## См. также  
 [Вызовы функций Naked](../Topic/Naked%20Function%20Calls.md)