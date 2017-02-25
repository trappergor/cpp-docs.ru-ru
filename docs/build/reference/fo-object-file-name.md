---
title: "/Fo (имя объектного файла) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Fo"
  - "VC.Project.VCCLCompilerTool.ObjectFile"
  - "VC.Project.VCCLWCECompilerTool.ObjectFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fo - параметр компилятора [C++]"
  - "Fo - параметр компилятора [C++]"
  - "-Fo - параметр компилятора [C++]"
  - "файлы объектов, именование"
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /Fo (имя объектного файла)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает имя файла или каталога объектного файла \(OBJ\), которое следует использовать вместо имени по умолчанию.  
  
## Синтаксис  
  
```  
/Fopathname  
```  
  
## Заметки  
 Если этот параметр не используется, для объектного файла используется базовое имя файла исходного кода и расширение OBJ.  Можно использовать любое желаемое имя и расширение, но при этом рекомендуется использовать расширение OBJ.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Откройте папку **C\/C\+\+**.  
  
3.  Выберите страницу свойств **Выходные файлы**.  
  
4.  Измените значение свойства **Имя объектного файла**.  В среде разработки объектный файл должен иметь расширение OBJ.  
  
### Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>.  
  
## Пример  
 При использовании следующей командной строки в существующем каталоге \\OBJECT на диске B будет создан объектный файл с именем THIS.obj:  
  
```  
CL /FoB:\OBJECT\ THIS.C  
```  
  
## См. также  
 [Параметры выходного файла \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)   
 [Указание пути](../Topic/Specifying%20the%20Pathname.md)