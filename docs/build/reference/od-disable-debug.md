---
title: "/Od (Выключение (отладчика)) | Microsoft Docs"
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
  - "/od"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Od - параметр компилятора [C++]"
  - "отключить (отладку) - параметр компилятора [C++]"
  - "отключить оптимизацию"
  - "быстрая компиляция"
  - "отключить оптимизацию"
  - "Od - параметр компилятора [C++]"
  - "-Od - параметр компилятора [C++]"
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Od (Выключение (отладчика))
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выключает все оптимизации в программе и ускоряет компиляцию.  
  
## Синтаксис  
  
```  
/Od  
```  
  
## Заметки  
 Этот параметр выбирается по умолчанию.  Т.к. **\/Od** отключает перемещение кода, это упрощает процесс отладки.  Дополнительные сведения о параметрах компилятора для отладки см. в разделе [\/Z7, \/Zi, \/ZI \(формат отладочной информации\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Перейдите на страницу свойств **Оптимизация**.  
  
4.  Измените значение свойства **Оптимизация**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.  
  
## См. также  
 [Параметры \/O \(оптимизация кода\)](../../build/reference/o-options-optimize-code.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)   
 [\/Z7, \/Zi, \/ZI \(формат отладочной информации\)](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md)