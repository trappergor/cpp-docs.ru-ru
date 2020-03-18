---
title: Управляемые компилятором параметры LINK
ms.date: 11/04/2016
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
ms.openlocfilehash: f631d0ebbbd9e60fe5d54aac6fb158461d3f4d38
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440107"
---
# <a name="compiler-controlled-link-options"></a>Управляемые компилятором параметры LINK

Компилятор CL автоматически вызывает LINK, если не указан параметр/c. CL предоставляет некоторый контроль над компоновщиком с помощью параметров командной строки и аргументов. В следующей таблице перечислены функции, которые влияют на компоновку в CL.

|Спецификация CL|Действие CL, которое влияет на связь|
|----------------------|---------------------------------|
|Любое расширение имени файла, отличное от. c,. CXX,. cpp или. def|Передает имя файла в качестве входных данных для ссылки|
|*имя файла*. def|Передает/DEF:*filename*. def|
|/F*число*|Передача значения/STACK:*Number*|
|*Имя файла* /FD|Передает/PDB:*filename*|
|*Имя файла* /Fe|Передает/OUT:*filename*|
|*Имя файла* /FM|Передает/MAP:*filename*|
|/Gy|Создает упакованные функции (COMDAT); включает компоновку на уровне функций|
|/LD|Передача/DLL|
|/LDd|Передача/DLL|
|/link|Передает оставшуюся часть командной строки для СВЯЗЫВАНИЯ|
|/MD или/MT|Помещает имя библиотеки по умолчанию в OBJ-файл|
|/MDd или/MTd|Помещает имя библиотеки по умолчанию в OBJ-файл. Определяет символ **_DEBUG**|
|/nologo|Передает/NOLOGO|
|/ZD|Передает/DEBUG|
|/Zi или/Z7|Передает/DEBUG|
|/Zl|Исключает имя библиотеки по умолчанию из OBJ-файла|

Дополнительные сведения см. в разделе [параметры компилятора компилятором MSVC](compiler-options.md).

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
