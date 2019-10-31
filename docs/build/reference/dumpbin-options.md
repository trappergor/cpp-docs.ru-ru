---
title: Параметры DUMPBIN
ms.date: 10/24/2019
f1_keywords:
- dumpbin
helpviewer_keywords:
- DUMPBIN program, options
ms.assetid: 563b696e-7599-4480-94b9-014776289ec8
ms.openlocfilehash: 81c66f1971294531a2904a0b681819476bcc1eb2
ms.sourcegitcommit: 6ed1bc5b26dc60a780c1fc5f2f19d57ba1dc47d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73144555"
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

- [/ERRORREPORT: {NONE | ЗАПРОС | ОЧЕРЕДЬ | ОБМЕНА](errorreport-dumpbin-exe.md)

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

Чтобы получить список параметров, поддерживаемых программой DUMPBIN в командной строке, используйте параметр **/?.** функцию.

## <a name="see-also"></a>См. также

[Дополнительные\ средств сборки компилятором MSVC](c-cpp-build-tools.md)
\ [командной строки DUMPBIN](dumpbin-command-line.md)
[Справочник по DUMPBIN](dumpbin-reference.md)
