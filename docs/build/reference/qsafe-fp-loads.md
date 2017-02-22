---
title: "/Qsafe_fp_loads | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 2b2ce52d-ba57-4bd3-a739-47a7f8bfaba9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /Qsafe_fp_loads
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Для инструкций перемещения целого числа для плавающей запятой и отключение некоторых с плавающей запятой оптимизации загрузки.  
  
## Синтаксис  
  
```  
/Qsafe_fp_loads  
```  
  
## Заметки  
 **\/Qsafe\_fp\_loads** доступно только в компиляторах этот целевой объект x86; он недоступен в компиляторах, целевой объект x64 или ARM.  
  
 **\/Qsafe\_fp\_loads** заставляет компилятор использовать инструкции вместо перемещения целые числа с плавающей запятой инструкций перемещения перемещение данных между памятью и регистрами MMX.  Этот параметр также отключает оптимизацию для загрузки с плавающей запятой, которые могут быть загружены в указанных расположениях, если значение может вызвать исключение, загрузка\- для примера, значение Nan нескольких элементов управления.  
  
 Этот параметр переопределен [\/fp: за исключением](../../build/reference/fp-specify-floating-point-behavior.md).  **\/Qsafe\_fp\_loads** определяет подмножество расширения функциональности компилятора, определенное **\/fp:except**.  
  
 **\/Qsafe\_fp\_loads** несовместимо с [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) и [\/fp: быстрый](../../build/reference/fp-specify-floating-point-behavior.md).  Параметры компилятора с плавающей запятой Дополнительные сведения о см. в разделе [\/fp \(Определение поведения с плавающей запятой\)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Выберите папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Параметры \/Q \(низкоуровневые операции\)](../../build/reference/q-options-low-level-operations.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)