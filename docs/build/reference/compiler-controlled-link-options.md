---
title: "Управляемые компилятором параметры LINK | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc899fc7f1fc8c1805648e72e14ef13853841c90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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