---
title: Управляемые компилятором параметры LINK | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d99a05b5f9c4d97fd42328a41ad3fe054ab42cd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="compiler-controlled-link-options"></a>Compiler-Controlled LINK Options
CL-компилятор автоматически вызывает LINK, если не указан параметр/c. CL предоставляет определенные возможности управления компоновщиком с помощью командной строки для параметров и аргументов. В следующей таблице перечислены возможности CL компоновщиком.  
  
|Спецификация CL|CL действие, которое влияет на ССЫЛКУ|  
|----------------------|---------------------------------|  
|Любое расширение имени файла, отличный от .c, .cxx, .cpp или .def|Передает имя файла в качестве входных данных для СВЯЗИ|  
|*Имя файла*.def|/ DEF передает:*filename*.def|  
|/F*номер*|Передает/Stack:*номер*|  
|Параметр /Fd*имя файла*|Передает/PDB:*имя файла*|  
|/FE*имя файла*|Передает/OUT:*имя файла*|  
|Параметр /FM*имя файла*|Передает/MAP:*имя файла*|  
|/Gy|Создает упакованных функций (COMDAT); Включает компоновку на уровне функций|  
|/LD|Передает/DLL|  
|/LDd|Передает/DLL|  
|/link|Передает в программу LINK остаток командной строки|  
|/MD или/MT|Помещает в OBJ-файле имя библиотеки по умолчанию|  
|/ MDd или/MTd|Устанавливает имя библиотеки по умолчанию в OBJ-файле. Определяет символ **_DEBUG**|  
|/nologo|Передает/nologo|  
|/ Zd|Передает/Debug|  
|ZI или/Z7|Передает/Debug|  
|/Zl|Опускает имя библиотеки по умолчанию из OBJ-файл|  
  
 Дополнительные сведения см. в разделе [Параметры компилятора](../../build/reference/compiler-options.md).  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)