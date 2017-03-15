---
title: "/ZW (компиляция среды выполнения Windows) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.CompileAsWinRT"
  - "/zw"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ZW"
  - "/ZW - параметр компилятора"
  - "параметр компилятора среды выполнения Windows"
  - "-ZW"
  - "-ZW - параметр компилятора"
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /ZW (компиляция среды выполнения Windows)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Компилирует исходный код для поддержки [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../Token/cppwrt_short_md.md)]\) при создании приложений [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  
  
 Если при компиляции используется параметр **\/ZW**, также необходимо указать параметр **\/EHsc**.  
  
## Синтаксис  
  
```cpp  
/ZW /EHsc /ZW:nostdlib /EHsc  
```  
  
## Аргументы  
 nostdlib  
 Указывает на то, что Platform.winmd, Windows.Foundation.winmd и другие файлы метаданных Windows по умолчанию \(WINMD\) не включаются в компиляцию автоматически.  Вместо этого необходимо использовать параметр компилятора [\/FU \(название файла с принудительно используемым атрибутом \#using\)](../../build/reference/fu-name-forced-hash-using-file.md), чтобы явным образом указать файлы метаданных Windows.  
  
## Заметки  
 При указании параметра **\/ZW** компилятор поддерживает следующие возможности:  
  
-   файлы метаданных, пространства имен, типы данных и функции, требуемые приложению для выполнения в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)];  
  
-   автоматический подсчет ссылок для объектов [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] и автоматическое удаление объекта в случае, если число ссылок становится равным нулю.  
  
 Так как инкрементный компоновщик не поддерживает метаданные Windows, включенные в файлы OBJ при использовании параметра **\/ZW**, параметр [\/Gm \(включение минимального перепостроения\)](../../build/reference/gm-enable-minimal-rebuild.md) несовместим с **\/ZW**.  
  
 Для получения дополнительной информации см. [Справочник по языку C\+\+](../Topic/Visual%20C++%20Language%20Reference%20\(C++-CX\).md).  
  
## Требования  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)