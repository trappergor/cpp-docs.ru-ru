---
title: Средства сборки дополнительных MSVC
ms.date: 05/06/2019
f1_keywords:
- c.build
helpviewer_keywords:
- builds [C++], C/C++ tools
- tools [C++], build
ms.assetid: 48d9daf4-6bbf-473a-8ce2-bf2923b69f80
ms.openlocfilehash: 59c9cb4527de878b06cbb6a7b3abe921e9a60107
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220216"
---
# <a name="additional-msvc-build-tools"></a>Средства сборки дополнительных MSVC

Visual Studio предоставляет следующие служебные программы командной строки для просмотра и управления данными выходные данные сборки:


- [LIB. EXE](lib-reference.md) используется для создания и управления ими библиотеку общих объекта файла формат COFF объектных файлов. Он также может использоваться для создания файлов экспорта и импорта библиотеки в экспортированные справочные определения.

- [(ПРОГРАММА EDITBIN). EXE](editbin-reference.md) используется для изменения COFF двоичные файлы.

- [(ПРОГРАММА DUMPBIN). EXE](dumpbin-reference.md) отображает сведения о COFF двоичные файлы (например, таблица символов).

- [NMAKE](nmake-reference.md) считывается и выполняется сборочных файлов проекта.

- [ERRLOOK](value-edit-control.md), программа поиска ошибок, извлекает системное сообщение об ошибке или Ошибка модуля в зависимости от введенное значение.

- [XDCMake](xdcmake-reference.md). Помечено toolfor, обработка файлов исходного кода, которые содержат комментарии к документации с XML-теги.

- [BSCMAKE. EXE](bscmake-reference.md) (предоставляется только для обратной совместимости) создает файл информации (BSC-файл), содержащий сведения о символах (классы, функции, данные, макросы и типы) в программе. Просмотреть эти сведения в окнах в среде разработки. (BSC-файла можно также создавать в среде разработки.)

## <a name="see-also"></a>См. также

[Справочные сведения о сборке C/C++](c-cpp-building-reference.md)<br/>
[Декорированные имена](decorated-names.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
