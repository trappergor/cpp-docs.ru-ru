---
title: /SYMBOLS
ms.date: 09/05/2018
f1_keywords:
- /symbols
helpviewer_keywords:
- symbols, dumping
- public symbols
- symbols, displaying COFF symbol table
- symbol tables
- SYMBOLS dumpbin option
- /SYMBOLS dumpbin option
- -SYMBOLS dumpbin option
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
ms.openlocfilehash: 4aa6702cfa13523d64553041af4a18270d9babb3
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421484"
---
# <a name="symbols"></a>/SYMBOLS

```
/SYMBOLS
```

Этот параметр отображает таблицей символов COFF. Таблицы символов есть во всех объектных файлов. Таблица символов COFF появляется в файл изображения, только в том случае, если он связан с параметром/Debug.

Ниже приведено описание выходных данных для/symbols. Дополнительные сведения о значении/Symbols выходных данных может быть найдена в winnt.h (IMAGE_SYMBOL и IMAGE_AUX_SYMBOL) или документации COFF.

Рассмотрим следующий пример дампа:

```
Dump of file main.obj
File Type: COFF OBJECT

COFF SYMBOL TABLE
000 00000000 DEBUG    notype       Filename     | .file
    main.cpp
002 000B1FDB ABS      notype       Static       | @comp.id
003 00000000 SECT1    notype       Static       | .drectve
    Section length     26, #relocs    0, #linenums    0, checksum 722C964F
005 00000000 SECT2    notype       Static       | .text
    Section length     23, #relocs    1, #linenums    0, checksum 459FF65F, selection    1 (pick no duplicates)
007 00000000 SECT2    notype ()    External     | _main
008 00000000 UNDEF    notype ()    External     | ?MyDump@@YAXXZ (void __cdecl MyDump(void))

String Table Size = 0x10 bytes

  Summary

         26 .drectve
         23 .text
```

## <a name="remarks"></a>Примечания

Следующие описания, для строки, начинающиеся с номера символа, описываются столбцы, содержащие сведения, относящиеся к пользователям:

- Первое трехзначное число — это индекс или номер символа.

- Если третий столбец содержит раздел на MBF*x*, этот символ определен в этом разделе объектного файла. Но если UNDEF, не определен в этом объекте и должны быть разрешены в другом месте.

- Пятый столбец (Static, External) указывает, виден ли символ только внутри этого объекта, или это открытый (видимым извне). Статический символ _sym не будет скомпонован с общедоступным символом _sym; Это будут два разных экземпляра функций с именем _sym.

Последний столбец в нумерованной строке является имя символа и оба непараметризованных.

Только [/Headers](../../build/reference/headers.md) параметр (программа DUMPBIN) доступен для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)
