---
title: Параметры DUMPBIN
description: Справочное руководство по параметрам командной строки программы Microsoft DUMPBIN.
ms.date: 02/09/2020
helpviewer_keywords:
- DUMPBIN program, options
ms.assetid: 563b696e-7599-4480-94b9-014776289ec8
ms.openlocfilehash: 54f5a22808026f4442f85d5e53a0805702e05868
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440040"
---
# <a name="dumpbin-options"></a>Параметры DUMPBIN

Параметр состоит из *спецификатора Option*, который является либо тире (`-`), либо косой чертой (`/`), за которой следует имя параметра. Имена параметров не могут быть сокращены. Некоторые параметры принимают аргументы, указанные после двоеточия (`:`). В спецификации параметров не допускаются пробелы и символы табуляции. Используйте один или несколько пробелов или символов табуляции для разделения спецификаций параметров в командной строке. Имена параметров и их ключевые слова или имена файлов не учитывают регистр. Большинство параметров применяются ко всем двоичным файлам, но несколько применимы только к определенным типам файлов. По умолчанию программа DUMPBIN отправляет сведения в стандартный вывод. Используйте параметр [/out](out-dumpbin.md) для отправки выходных данных в файл.

## <a name="options-list"></a>Список параметров

DUMPBIN имеет следующие параметры.

- [/ALL](all.md)

- [/ARCHIVEMEMBERS](archivemembers.md)

- [/CLRHEADER](clrheader.md)

- [/DEPENDENTS](dependents.md)

- [/DIRECTIVES](directives.md)

- [/DISASM\[: {BYTEs\|BYTEs}\]](disasm.md)

- [/errorreport: {None | ЗАПРОС | ОЧЕРЕДЬ | SEND}](errorreport-dumpbin-exe.md) (не рекомендуется)

- [/EXPORTS](dash-exports.md)

- [/FPO](fpo.md)

- [/HEADERS](headers.md)

- [/IMPORTS\[: имя файла\]](imports-dumpbin.md)

- [/LINENUMBERS](linenumbers.md)

- [\[/ЛИНКЕРМЕМБЕР: {1 | 2}\]](linkermember.md)

- [/LOADCONFIG](loadconfig.md)

- [/нопдб](nopdb.md)

- [/OUT: имя файла](out-dumpbin.md)

- [/PDATA](pdata.md)

- [/ПДБПАС\[: verbose\]](pdbpath.md)

- [/РАНЖЕЕ: Вамин\[, Вамакс\]](range.md)

- [/РАВДАТА\[: {NONE\|1\|2\|4\|8}\[, #\]\]](rawdata.md)

- [/RELOCATIONS](relocations.md)

- [/SECTION: имя](section-dumpbin.md)

- [/SUMMARY](summary.md)

- [/SYMBOLS](symbols.md)

- [/TLS](tls.md)

Чтобы получить список параметров, поддерживаемых программой DUMPBIN в командной строке, используйте параметр **/?.** предложения.

## <a name="see-also"></a>См. также раздел

[Дополнительные\ средств сборки компилятором MSVC](c-cpp-build-tools.md)
\ [командной строки DUMPBIN](dumpbin-command-line.md)
[Справочник по DUMPBIN](dumpbin-reference.md)
