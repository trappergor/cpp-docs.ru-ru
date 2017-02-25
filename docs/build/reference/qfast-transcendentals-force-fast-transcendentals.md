---
title: "/Qfast_transcendentals (принудительное использование быстрых трансцендентных функций) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Qfast_transcendentals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Qfast_transcendentals"
  - "Быстрые трансцендентные функции - принудительное использование"
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /Qfast_transcendentals (принудительное использование быстрых трансцендентных функций)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот параметр создает встроенный код для трансцендентной функции.  
  
## Синтаксис  
  
```  
/Qfast_transcendentals  
```  
  
## Заметки  
 Данный параметр компилятора принудительно преобразует трансцендентные функции во встроенный код с целью повышения быстродействия.  Данный параметр работает только вместе с параметром **\/fp:except** или **\/fp:precise**.  Создание встроенного кода для трансцендентных функций является поведением по умолчанию при использовании параметра **\/fp:fast**.  
  
 Данный параметр несовместим с параметром **\/fp:strict**.  Дополнительные сведения о параметрах компилятора с плавающей точкой см. в разделе [\/fp \(Определение поведения с плавающей запятой\)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Параметры \/Q \(низкоуровневые операции\)](../../build/reference/q-options-low-level-operations.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)