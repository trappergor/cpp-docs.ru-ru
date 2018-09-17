---
title: Справочник ЕDITBIN | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- editbin
dev_langs:
- C++
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 809d1d4f25611b2310d651702f01e1e98888ad4a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699951"
---
# <a name="editbin-reference"></a>Справочник ЕDITBIN

Двоичный редактор файла COFF Майкрософт ((программа EDITBIN). (EXE) изменяет двоичные файлы общих объекта файла формат COFF. (Программа EDITBIN) можно использовать для изменения объектных файлов, исполняемых файлов и библиотек динамической компоновки (DLL).

> [!NOTE]
>  Это средство можно запустить только из командной строки Visual Studio. В системной командной строке или проводнике это невозможно.

(Программа EDITBIN) недоступен для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора. Изменения в двоичные файлы, созданные с параметром /GL будет достигаться компиляцию и компоновку.

- [Командная строка EDITBIN](../../build/reference/editbin-command-line.md)

- [Параметры EDITBIN](../../build/reference/editbin-options.md)

## <a name="see-also"></a>См. также

[Средства сборки С/C++](../../build/reference/c-cpp-build-tools.md)