---
title: "/X (Отклонение стандартных путей включения) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/x"
  - "VC.Project.VCCLCompilerTool.IgnoreStandardIncludePath"
  - "VC.Project.VCCLWCECompilerTool.IgnoreStandardIncludePath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/X - параметр компилятора [C++]"
  - "игнорировать стандартные пути включения - параметр компилятора"
  - "каталоги включений, игнорировать стандартные"
  - "включить файлы, игнорировать стандартный путь"
  - "X - параметр компилятора"
  - "-X - параметр компилятора [C++]"
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /X (Отклонение стандартных путей включения)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Запрещает компилятору поиск файлов включения в каталогах, указанных в переменных среды PATH и INCLUDE.  
  
## Синтаксис  
  
```  
/X  
```  
  
## Заметки  
 Данный параметр можно использовать с параметром [\/I \(дополнительные каталоги включения\)](../../build/reference/i-additional-include-directories.md) \(**\/I**`directory`\).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Щелкните страницу свойств **Препроцессор**.  
  
4.  Измените свойство **Отклонение стандартных путей включения**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>.  
  
## Пример  
 В следующей команде `/X` инструктирует компилятор отклонить расположения, указанные в переменных среды PATH и INCLUDE, а `/I` указывает каталог, в котором можно увидеть файлы включения:  
  
```  
CL /X /I \ALT\INCLUDE MAIN.C  
```  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)