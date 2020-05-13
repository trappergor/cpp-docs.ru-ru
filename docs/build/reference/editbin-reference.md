---
title: Справочник ЕDITBIN
ms.date: 11/04/2016
f1_keywords:
- editbin
helpviewer_keywords:
- binary data, editing
- object files, modifying
- EDITBIN program
- COFF files, editing
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
ms.openlocfilehash: 266347de063b4e050cb032aa2d8d74e7934b8081
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328339"
---
# <a name="editbin-reference"></a>Справочник ЕDITBIN

Редактор двоичного файла Microsoft COFF (EDITBIN. EXE) изменяет двоичные файлы Common Object File Format (COFF). Можно использовать EDITBIN для изменения файлов объектов, исполняемых файлов и библиотек динамической ссылки (DLL).

> [!NOTE]
> Запустить этот инструмент можно только с запроса команды Visual Studio. В системной командной строке или проводнике это невозможно.

EDITBIN недоступен для использования в файлах, созданных с опцией компилятора [/GL.](gl-whole-program-optimization.md) Любые изменения в бинарных файлах, производимых с /GL, должны быть достигнуты путем перекомпиляции и ссылок.

- [Командная строка EDITBIN](editbin-command-line.md)

- [Варианты EDITBIN](editbin-options.md)

## <a name="see-also"></a>См. также раздел

[Дополнительные инструменты сборки MSVC](c-cpp-build-tools.md)
