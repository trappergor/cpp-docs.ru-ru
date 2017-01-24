---
title: "/C (сохранять комментарии во время предварительной обработки) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.KeepComments"
  - "/c"
  - "VC.Project.VCCLWCECompilerTool.KeepComments"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/c - параметр компилятора [C++]"
  - "c - параметр компилятора [C++]"
  - "-c - параметр компилятора [C++]"
  - "комментарии, не удаление во время предварительной обработки"
  - "сохранять комментарии во время предварительной обработки"
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /C (сохранять комментарии во время предварительной обработки)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сохраняет комментарии на этапе предварительной обработки.  
  
## Синтаксис  
  
```  
/C  
```  
  
## Заметки  
 Этот параметр компилятора требует указания параметра **\/E**, **\/P** или **\/EP**.  
  
 Код из следующего примера отобразит комментарий исходного кода.  
  
```  
// C_compiler_option.cpp  
// compile with: /E /C /c  
int i;   // a variable  
```  
  
 Этот код будет приводить к следующему результату.  
  
```  
#line 1 "C_compiler_option.cpp"  
int i;   // a variable  
```  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Щелкните страницу свойств **Препроцессор**.  
  
4.  Измените значение свойства **Оставлять комментарии**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>.  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)   
 [\/E \(Предварительная обработка до stdout\)](../../build/reference/e-preprocess-to-stdout.md)   
 [\/P \(вывод результатов предварительной обработки в файл\)](../../build/reference/p-preprocess-to-a-file.md)   
 [\/EP \(предварительная обработка в поток стандартных выходных файлов без директив \#line\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)