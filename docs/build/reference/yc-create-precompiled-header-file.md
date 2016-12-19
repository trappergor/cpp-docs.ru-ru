---
title: "/Yc (создать предварительно скомпилированный заголовочный файл) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.UsePrecompiledHeader"
  - "/yc"
  - "VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough"
  - "VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader"
  - "VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PCH-файлы, создание"
  - "/Yc - параметр компилятора [C++]"
  - "PCH-файлы, создание"
  - "файлы предкомпилированного заголовка, создание"
  - "Yc - параметр компилятора [C++]"
  - "-Yc - параметр компилятора [C++]"
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Yc (создать предварительно скомпилированный заголовочный файл)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предписывает компилятору создание предварительно скомпилированного заголовочного файла \(.pch\), представляющего состояние компиляции на определенном этапе.  
  
## Синтаксис  
  
```  
/Yc[filename]  
```  
  
## Аргументы  
 `filename`  
 Указывает файл заголовков \(H\).  При использовании этого аргумента компилятор компилирует весь код, включая H\-файл.  
  
## Заметки  
 Если **\/Yc** указан без аргумента, компилятор компилирует весь код до конца базового исходного файла или до точки в базовом файле, где возникло событие [hdrstop](../../preprocessor/hdrstop.md).  Итоговый PCH\-файл имеет то же базовое имя, что и базовый исходный файл, если не указано другое имя файла с помощью прагмы **hdrstop** или параметра **\/Fp**.  
  
 Предварительно скомпилированный код сохраняется в файле с именем, созданным из базового имени файла, указанного с помощью параметра **\/Yc** и с расширением PCH.  Чтобы указать имя для предварительно скомпилированного заголовочного файла, можно также использовать параметр [\/Fp \(имя PCH\-файла\)](../Topic/-Fp%20\(Name%20.Pch%20File\).md).  
  
 Если используется **\/Yc**`filename`, компилятор компилирует весь код, включая указанный файл для последующего использования с параметром **\/Yu**.  
  
 Если параметры **\/Yc**`filename` и [\/Yu \(использование файла предкомпилированного заголовка\)](../../build/reference/yu-use-precompiled-header-file.md)`filename` встречаются в одной командной строке и обеих ссылках или заключают в себе одинаковое имя файла, параметр **\/Yc**`filename` получает приоритет.  Это позволяет упростить создание файлов makefile.  
  
 Дополнительные сведения о предкомпилированных заголовках см. в разделах:  
  
-   [\/Y \(Предварительно скомпилированные заголовки\)](../../build/reference/y-precompiled-headers.md)  
  
-   [Создание файлов предкомпилированных заголовков](../../build/reference/creating-precompiled-header-files.md)  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Выберите файл CPP.  CPP\-файл должен включать H\-файл, который содержит сведения о предкомпилированных заголовках.  Параметр **\/Yc** проекта должен быть переопределен на уровне файла.  
  
2.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
3.  Откройте папку **C\/C\+\+**.  
  
4.  Щелкните страницу свойств **Предкомпилированные заголовки**.  
  
5.  Измените свойство **Создание\/использование PCH\-файла до файла включительно** или **Создание\/использование предкомпилированного заголовка**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. разделы <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.  
  
## Пример  
 Рассмотрим следующий код.  
  
```  
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
...  
```  
  
 При компилировании этого кода с помощью команды `CL /YcMYAPP.H PROG.CPP` компилятор сохраняет всю предварительную обработку для AFXWIN.h, RESOURCE.h и MYAPP.h в файле предварительно скомпилированного заголовочного файла с именем MYAPP.pch.  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)