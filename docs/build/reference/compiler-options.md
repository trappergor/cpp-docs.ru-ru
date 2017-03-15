---
title: "Параметры компилятора | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe - компилятор"
  - "параметры компилятора, C++"
  - "компилятор IPF (Visual C++)"
  - "компилятор Itanium (Visual C++)"
  - "компилятор x64 (Visual C++)"
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Параметры компилятора
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cl.exe — это средство, предназначенное для управления компиляторами и компоновщиком Microsoft C и C\+\+. cl.exe можно запускать только в операционных системах, поддерживающих Microsoft Visual Studio.  
  
> [!NOTE]
>  Этот инструмент можно запустить только из командной строки [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  Его невозможно запустить из системной командной строки или из проводника.  
  
 Компиляторы создают объектные OBJ\-файлы в формате COFF.  Компоновщик создает исполняемые файлы \(EXE\) или библиотеки динамической компоновки \(DLL\).  
  
 Следует отметить, что все параметры компилятора чувствительны к регистру символов.  
  
 Для компиляции без компоновки следует использовать параметр [\/c](../../build/reference/c-compile-without-linking.md).  
  
## Поиск параметра  
 Чтобы найти конкретный параметр компилятора см. один из следующих списков.  
  
-   [Параметры компилятора в алфавитном порядке](../../build/reference/compiler-options-listed-alphabetically.md)  
  
-   [Параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md)  
  
## Установка параметров  
 В разделах, посвященных отдельным параметрам компилятора, содержатся сведения о настройке параметров в среде разработки.  Сведения о задании параметров за пределами среды разработки см. в разделе:  
  
-   [Синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md)  
  
-   [Командные файлы компилятора CL](../../build/reference/cl-command-files.md)  
  
-   [Переменные среды CL](../../build/reference/cl-environment-variables.md)  
  
## Связанные средства построения  
 Для построения выходного файла следует использовать средство [NMAKE](../../build/nmake-reference.md).  
  
 Для включения поддержки просмотра классов следует использовать [BSCMAKE](../../build/reference/bscmake-reference.md).  
  
 [Параметры компоновщика](../../build/reference/linker-options.md) также влияют на построение программы.  
  
## См. также  
 [Образец построения C\/C\+\+](../Topic/C-C++%20Building%20Reference.md)   
 [Настройка параметров компилятора](../Topic/Setting%20Compiler%20Options.md)   
 [Быстрая компиляция](../Topic/Fast%20Compilation.md)   
 [Вызов компоновщика компилятором CL](../../build/reference/cl-invokes-the-linker.md)