---
title: "/Qimprecise_fwaits (Удалить ожидания в блоке try) | Microsoft Docs"
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
  - "/Qimprecise_fwaits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Qimprecise_fwaits - параметр компилятора (C++)"
  - "-Qimprecise_fwaits - параметр компилятора (C++)"
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Qimprecise_fwaits (Удалить ожидания в блоке try)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот параметр удаляет внутренние команды `fwait` в блоках `try` при использовании параметра компилятора [\/fp:except](../../build/reference/fp-specify-floating-point-behavior.md).  
  
## Синтаксис  
  
```  
/Qimprecise_fwaits  
```  
  
## Заметки  
 Этот параметр не действует, если **\/fp:except** не указан.  Если указан параметр **\/fp:except**, компилятор вставит команду `fwait` вокруг каждой линии кода в блоке `try`.  В этом случае компилятор может указать определенную строку кода, которая вызвала исключение.  **\/Qimprecise\_fwaits** удаляет внутренние инструкции `fwait`, оставляя только ожидания вокруг блока `try`.  Это повышает производительность, но компилятор может только указать, какой блок `try` вызывает исключение, но не какая строка.  
  
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