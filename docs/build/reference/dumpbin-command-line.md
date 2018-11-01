---
title: Командная строка DUMPBIN
ms.date: 11/04/2016
f1_keywords:
- dumpbin
helpviewer_keywords:
- DUMPBIN program, command line
ms.assetid: e6ad17d3-965d-41aa-9dfd-75bb073718d4
ms.openlocfilehash: 72b907abbbb52a881feb415e47a768e61a9819ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539286"
---
# <a name="dumpbin-command-line"></a>Командная строка DUMPBIN

Чтобы запустить (программа DUMPBIN), используйте следующий синтаксис:

```
DUMPBIN [options] files...
```

Укажите один или несколько двоичных файлов, а также любые параметры, необходимые для управления данными. (Программа DUMPBIN) отображает сведения в стандартный вывод. Можно перенаправить его в файл или используйте параметр/out, чтобы указать имя файла для выходных данных.

При запуске программы DUMPBIN для файла без указания параметра DUMPBIN отображает параметра/Summary выходных данных.

При вводе команды `dumpbin` без других командной строки ввода, DUMPBIN отображает инструкцию использования параметров.

## <a name="see-also"></a>См. также

[Средства сборки С/C++](../../build/reference/c-cpp-build-tools.md)<br/>
[Справочник DUMPBIN](../../build/reference/dumpbin-reference.md)