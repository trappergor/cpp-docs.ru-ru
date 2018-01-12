---
title: "Параметры компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler
- IPF Visual C++ compiler
- Itanium Visual C++ compiler
- compiler options, C++
- x64 Visual C++ compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c433abea04ff81c69fe1b73569ea7e043e6e81ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-options"></a>Параметры компилятора
CL.exe — это средство, который управляет Microsoft C и C++ компилятора и компоновщика. CL.exe может выполняться только в операционных системах, поддерживающих Microsoft Visual Studio.  
  
> [!NOTE]
>  Это средство можно запустить только из командной строки [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. В системной командной строке или проводнике это невозможно.  
  
 Компиляторы создают общий объект файла формат COFF объектных файлах (.obj). Компоновщик создает исполняемые файлы (.exe) или библиотеки динамической компоновки (DLL).  
  
 Обратите внимание, что все параметры компилятора чувствительны к регистру.  
  
 Для компиляции без компоновки, используйте [/c](../../build/reference/c-compile-without-linking.md).  
  
## <a name="finding-an-option"></a>Поиск параметра  
 Чтобы найти конкретный параметр компилятора, см. в одном из следующих списков:  
  
-   [Параметры компилятора в алфавитном порядке](../../build/reference/compiler-options-listed-alphabetically.md)  
  
-   [Параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md)  
  
## <a name="specifying-options"></a>Указание параметров  
 В этом разделе для каждого параметра компилятора обсуждается, как это можно сделать в среде разработки. Сведения об установке параметров вне среды разработки см. в разделе:  
  
-   [Синтаксис командной строки компилятора](../../build/reference/compiler-command-line-syntax.md)  
  
-   [Командные файлы компилятора CL](../../build/reference/cl-command-files.md)  
  
-   [Переменные среды CL](../../build/reference/cl-environment-variables.md)  
  
## <a name="related-build-tools"></a>Связанные средства построения  
 Используйте [NMAKE](../../build/nmake-reference.md) для создания выходного файла.  
  
 Используйте [BSCMAKE](../../build/reference/bscmake-reference.md) для поддержки просмотра классов.  
  
 [Параметры компоновщика](../../build/reference/linker-options.md) также влияют на построение программы.  
  
## <a name="see-also"></a>См. также  
 [Справочные сведения о построении C/C++](../../build/reference/c-cpp-building-reference.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Быстрая компиляция](../../build/reference/fast-compilation.md)   
 [Вызов компоновщика компилятором CL](../../build/reference/cl-invokes-the-linker.md)