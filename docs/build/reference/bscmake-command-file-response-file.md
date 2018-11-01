---
title: Командный файл BSCMAKE (файл отклика)
ms.date: 11/04/2016
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
ms.openlocfilehash: 6be6dae2ef3dd729819a5eccba5e86df479ab5ad
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587317"
---
# <a name="bscmake-command-file-response-file"></a>Командный файл BSCMAKE (файл отклика)

Можно указать часть или все входные данные командной строки в файле команд. Укажите командный файл, используя следующий синтаксис:

```
BSCMAKE @filename
```

Допускается только один командный файл. Можно указать путь с *filename*. Перед *filename* с символа (**\@**). BSCMAKE не допускает расширение. Можно указать дополнительные *sbrfiles* в командной строке после *filename*. Командный файл — это текстовый файл, содержащий входные данные (BSCMAKE) в том же порядке, как его следует указать в командной строке. Аргументы командной строки следует разделяйте один или несколько пробелов, табуляции и символы новой строки.

Следующая команда вызывает использование командный файл BSCMAKE:

```
BSCMAKE @prog1.txt
```

Ниже приведен пример командного файла:

```
/n /v /o main.bsc /El
/S (
toolbox.h
verdate.h c:\src\inc\screen.h
)
file1.sbr file2.sbr file3.sbr file4.sbr
```

## <a name="see-also"></a>См. также

[Справочник ВSCMAKE](../../build/reference/bscmake-reference.md)