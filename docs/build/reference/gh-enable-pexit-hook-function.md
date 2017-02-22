---
title: "/GH (включить функцию-обработчик _pexit) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_pexit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Gh - параметр компилятора [C++]"
  - "_pexit - функция"
  - "Gh - параметр компилятора [C++]"
  - "-Gh - параметр компилятора [C++]"
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /GH (включить функцию-обработчик _pexit)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот параметр вызывает функцию `_pexit`  в конце каждого метода или функции.  
  
## Синтаксис  
  
```  
/GH  
```  
  
## Заметки  
 Функция `_pexit`  не является частью какой\-либо библиотеки, поэтому следует самостоятельно предоставить определение для `_pexit`.  
  
 Если вызов `_pexit` не планируется явно, нет необходимости предоставлять прототип.  Функция должна выглядеть так, как если бы она имела следующий прототип; на входе она должна занести содержимое всех регистров в стек и извлечь неизмененное содержимое стека на выходе:  
  
```  
void __declspec(naked) _cdecl _pexit( void );  
```  
  
 Функция `_pexit` аналогична функции `_penter`; пример создания функции `_pexit` см. в разделе [\/Gh \(Включение функции обработчика \_penter\)](../../build/reference/gh-enable-penter-hook-function.md).  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Введите параметры компилятора в поле **Дополнительные параметры**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)