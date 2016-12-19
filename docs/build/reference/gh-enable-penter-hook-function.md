---
title: "/Gh (Включение функции обработчика _penter) | Microsoft Docs"
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
  - "_penter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gh - параметр компилятора [C++]"
  - "_penter - функция"
  - "Gh - параметр компилятора [C++]"
  - "-Gh - параметр компилятора [C++]"
ms.assetid: 1510a082-8a0e-486e-a309-6add814b494f
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Gh (Включение функции обработчика _penter)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызывает функцию `_penter` при запуске каждого метода или функции.  
  
## Синтаксис  
  
```  
/Gh  
```  
  
## Заметки  
 Функция `_penter` не является частью библиотеки, поэтому следует самостоятельно предоставить определение для `_penter`.  
  
 Если явно не планируется вызов `_penter`, нет необходимости предоставлять прототип.  Функция должна выглядеть так, как если бы она имела следующий прототип; на входе она должна занести содержимое всех регистров в стек и извлечь неизмененное содержимое стека на выходе:  
  
```  
void __declspec(naked) _cdecl _penter( void );  
```  
  
 Это объявление недоступно для 64\-разрядных проектов.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Введите параметры компилятора в поле **Дополнительные параметры**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## Пример  
 Следующий код при компиляции с помощью **\/Gh**, показывает как `_penter` вызывается дважды, один раз при введении функции `main`, а второй раз при введении функции `x`.  
  
```  
// Gh_compiler_option.cpp  
// compile with: /Gh  
// processor: x86  
#include <stdio.h>  
void x() {}  
  
int main() {  
   x();  
}  
  
extern "C" void __declspec(naked) _cdecl _penter( void ) {  
   _asm {  
      push eax  
      push ebx  
      push ecx  
      push edx  
      push ebp  
      push edi  
      push esi  
    }  
  
   printf_s("\nIn a function!");  
  
   _asm {  
      pop esi  
      pop edi  
      pop ebp  
      pop edx  
      pop ecx  
      pop ebx  
      pop eax  
      ret  
    }  
}  
```  
  
  **В function\!**  
**В function\!**   
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)