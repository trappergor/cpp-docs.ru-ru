---
title: Средства построения C/C++ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- c.build
dev_langs:
- C++
helpviewer_keywords:
- builds [C++], C/C++ tools
- tools [C++], build
ms.assetid: 48d9daf4-6bbf-473a-8ce2-bf2923b69f80
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a6a223e092e7ad31dd263142d2a87712eaf556b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726041"
---
# <a name="cc-build-tools"></a>Средства построения С/C++

Visual C++ предоставляет следующие средства командной строки для просмотра и управления данными выходные данные сборки:

- [BSCMAKE. EXE](../../build/reference/bscmake-reference.md) создает файл информации (BSC-файл), содержащий сведения о символах (классы, функции, данные, макросы и типы) в программе. Просмотреть эти сведения в окнах в среде разработки. (BSC-файла можно также создавать в среде разработки.)

- [LIB. EXE](../../build/reference/lib-reference.md) используется для создания и управления ими библиотеку общих объекта файла формат COFF объектных файлов. Он также может использоваться для создания файлов экспорта и импорта библиотеки в экспортированные справочные определения.

- [(ПРОГРАММА EDITBIN). EXE](../../build/reference/editbin-reference.md) используется для изменения COFF двоичные файлы.

- [(ПРОГРАММА DUMPBIN). EXE](../../build/reference/dumpbin-reference.md) отображает сведения о COFF двоичные файлы (например, таблица символов).

- [NMAKE](../../build/nmake-reference.md) считывается и выполняется сборочных файлов проекта.

- [ERRLOOK](../../build/reference/value-edit-control.md), программа поиска ошибок, извлекает системное сообщение об ошибке или Ошибка модуля в зависимости от введенное значение.

## <a name="see-also"></a>См. также

[Справочные сведения о сборке C/C++](../../build/reference/c-cpp-building-reference.md)<br/>
[Декорированные имена](../../build/reference/decorated-names.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)