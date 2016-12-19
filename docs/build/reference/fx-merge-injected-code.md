---
title: "/Fx (объединение подставляемого кода) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.ExpandAttributedSource"
  - "/Fx"
  - "VC.Project.VCCLCompilerTool.ExpandAttributedSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fx - параметр компилятора [C++]"
  - "-Fx - параметр компилятора [C++]"
  - "введенный код"
  - "объединение введенного кода"
  - "/Fx - параметр компилятора [C++]"
ms.assetid: 14f0e301-3bab-45a3-bbdf-e7ce66f20560
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fx (объединение подставляемого кода)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает копию всех исходных файлов с подставляемым кодом, объединенным с исходным кодом.  
  
## Синтаксис  
  
```  
/Fx  
```  
  
## Заметки  
 Чтобы отделить объединенный исходный файл от оригинального исходного файла, **\/Fx** добавляет расширение MRG между именем файла и его расширением. Например, файл с именем MyCode.cpp, который включает код с атрибутами и собран с помощью с **\/Fx**, порождает файл с именем MyCode.mrg.cpp, который содержит следующий код:  
  
```  
//+++ Start Injected Code [no_injected_text(true)];      // Suppress injected text, it has // already been injected #pragma warning(disable: 4543) // Suppress warnings about skipping // injected text #pragma warning(disable: 4199) // Suppress warnings from attribute // providers //--- End Injected Code  
```  
  
 В MRG\-файле код, подставленный из\-за наличия атрибута, будет отделен следующим образом:  
  
```  
//+++ Start Injected Code ... //--- End Injected Code  
```  
  
 Атрибут [no\_injected\_text](../../windows/no-injected-text.md) встроен в MRG\-файл, что допускает компиляцию MRG\-файла без повторной подстановки текста.  
  
 Обратите внимание, что исходный MRG\-файл предназначен для представления исходного кода, подставленного компилятором. MRG\-файл может компилироваться или запускаться отличным от оригинального исходного файла образом.  
  
 Макросы не будут развернуты в MRG\-файле.  
  
 Если программа включает файл заголовка, который использует подставляемый код, **\/Fx** создает файл с расширением .mrg.h для этого заголовка.**\/Fx** не выполняет объединение для включаемых файлов, которые не используют подставляемый код.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Откройте страницу свойств **Выходные файлы**.  
  
4.  Измените свойство **Раскрывать атрибуты исходного кода**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExpandAttributedSource%2A>.  
  
## См. также  
 [Параметры выходного файла \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)