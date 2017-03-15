---
title: "Параметр /c (компиляция без связывания) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/c"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/c - параметр компилятора [C++]"
  - "c - параметр компилятора [C++]"
  - "-c - параметр компилятора [C++]"
  - "cl.exe - компилятор, компиляция без связывания"
  - "отмена связывания"
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Параметр /c (компиляция без связывания)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Запрет автоматического вызова программы LINK.  
  
## Синтаксис  
  
```  
/c  
```  
  
## Заметки  
 При компиляции с параметром **\/c** создаются только OBJ\-файлы.  В этом случае для выполнения этапа связывания в процессе построения следует явно вызвать программу LINK с указанием соответствующих файлов и параметров.  
  
 Во всех внутренних проектах среды разработки по умолчанию используется параметр **\/c**.  
  
### Установка данного параметра компилятора в среде разработки Visual Studio  
  
-   Данный параметр недоступен в среде разработки.  
  
### Установка данного параметра компилятора программным способом  
  
-   Сведения об установке этого параметра компилятора программным способом см. в описании свойства <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>.  
  
## Пример  
 При выполнении следующей команды создаются OBJ\-файлы FIRST.obj и SECOND.obj.  Файл THIRD.obj игнорируется.  
  
```  
CL /c FIRST.C SECOND.C THIRD.OBJ  
```  
  
 Чтобы создать исполняемый файл, следует вызвать программу LINK:  
  
```  
LINK firsti.obj second.obj third.obj /OUT:filename.exe  
```  
  
## См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)