---
title: Управляемые компилятором параметры LINK | Документация Майкрософт
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
ms.openlocfilehash: ee952fe5152d98aa33c4ef7e98f8a2eb3ef077be
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726431"
---
# <a name="compiler-controlled-link-options"></a>Compiler-Controlled LINK Options

CL-компилятор автоматически вызывает ССЫЛКУ, если не указано параметром. CL предоставляет определенные возможности управления компоновщиком с помощью командной строки для параметров и аргументов. В следующей таблице перечислены функции CL-компилятора, которые влияют на связывание.

|Спецификация CL|CL: действие, которое влияет на СВЯЗИ|
|----------------------|---------------------------------|
|Любое расширение имени файла, кроме .c, .cxx, .cpp или .def|Передает имя файла в качестве входных данных для ссылки|
|*Имя файла*.def|/ DEF передает:*filename*.def|
|/F*номер*|Число проходов/Stack:*номер*|
|/Fd*имя файла*|Передает/PDB:*имя файла*|
|/FE*имя файла*|Передает/OUT:*имя файла*|
|/FM*имя файла*|Число проходов/MAP:*имя файла*|
|/Gy|Создает упакованных функций (COMDAT); включает функцию компоновку на уровне|
|/LD|Передает/DLL|
|/LDd|Передает/DLL|
|/link|Передает остаток командной строки ссылки|
|/MD или/MT|Помещает имя библиотеки по умолчанию в OBJ-файле|
|/ MDd или/MTd|Помещает имя библиотеки по умолчанию в OBJ-файле. Определяет символ **_DEBUG**|
|/nologo|Передает/nologo|
|/ Zd|Передает/Debug|
|ZI или/Z7|Передает/Debug|
|/Zl|Опускает имя библиотеки по умолчанию из OBJ-файле|

Дополнительные сведения см. в разделе [Параметры компилятора](../../build/reference/compiler-options.md).

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)