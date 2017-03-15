---
title: "Параметр /nologo (отключение загрузочного объявление) (C/C++) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.SuppressStartupBanner"
  - "VC.Project.VCCLCompilerTool.SuppressStartupBanner"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/nologo - параметр компилятора [C++]"
  - "баннеры, отключение при загрузке"
  - "nologo - параметр компилятора [C++]"
  - "-nologo - параметр компилятора [C++]"
ms.assetid: 75930d8b-b11c-4db8-99e5-b52f97da0693
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Параметр /nologo (отключение загрузочного объявление) (C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Отключает отображение баннера с данными об авторских правах при запуске компилятора и дополнительных сообщений при компиляции.  
  
## Синтаксис  
  
```  
/nologo  
```  
  
## Заметки  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Общие**.  
  
4.  Измените значение свойства **Отключить приветствие при загрузке**.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.SuppressStartupBanner%2A>.  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)