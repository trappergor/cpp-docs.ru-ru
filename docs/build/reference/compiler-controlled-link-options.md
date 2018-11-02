---
title: Compiler-Controlled LINK Options
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
ms.openlocfilehash: 21d0baccaf74fc08bb110b0ae9f8b7dc108abd6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561581"
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