---
title: "/arch (x64) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /arch (x64)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает архитектуру для создания кода на платформе x64.  См. также [\/arch \(x86\)](../../build/reference/arch-x86.md) и [\/arch \(ARM\)](../../build/reference/arch-arm.md).  
  
## Синтаксис  
  
```  
/arch:[AVX|AVX2]  
```  
  
## Аргументы  
 **\/arch:AVX**  
 Позволяет использовать инструкции Intel AVX.  
  
 **\/arch:AVX2**  
 Позволяет использовать инструкции Intel AVX 2.  
  
## Заметки  
 **\/arch** влияет только на создание кода для собственных функций.  При компиляции с помощью [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) параметр **\/arch** не оказывает влияния на создание кода для управляемых функций.  
  
 Символ препроцессора `__AVX__` определяется, если указан параметр компилятора **\/arch:AVX**.  Символ препроцессора `__AVX2__` определяется, если указан параметр компилятора **\/arch:AVX2**.  Подробнее: [Предустановленный макрос](../../preprocessor/predefined-macros.md).  Параметр **\/arch:AVX2** появился в Visual Studio 2013 с обновлением 2 версии 12.0.34567.1.  
  
### Установка параметра компилятора \/arch:AVX или \/arch:AVX2 в Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Подробнее: [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Выберите папку **Свойства конфигурации**, а затем папку **C\/C\+\+**.  
  
3.  Выберете страницу свойств **Создание кода**.  
  
4.  В поле с раскрывающимся списком **Включить расширенный набор инструкций** выберите значение **Advanced Vector Extensions \(\/arch:AVX\)** или **Advanced Vector Extensions 2 \(\/arch:AVX2\)**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## См. также  
 [\/arch \(минимальная архитектура ЦП\)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)