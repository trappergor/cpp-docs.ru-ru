---
title: Командная строка DUMPBIN | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- dumpbin
dev_langs:
- C++
helpviewer_keywords:
- DUMPBIN program, command line
ms.assetid: e6ad17d3-965d-41aa-9dfd-75bb073718d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c9028cebd7c75bb37bbfa958186ebb2e5d206094
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724788"
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