---
title: Где следует определять макросы
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: 130863f8c5640a0c4915734732d93fc00d3d6479
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656252"
---
# <a name="where-to-define-macros"></a>Где следует определять макросы

Макросы определяются в командную строку, командный файл, файл makefile или файле Tools.ini.

В файле makefile или файле Tools.ini каждое определение макроса должны располагаться на отдельной строке и не может начинаться с пробела или табуляции. Игнорируются пробелы или знаки табуляции вокруг знака равенства. Все [строка символов](../build/defining-an-nmake-macro.md) являются литералами, в том числе заключающие кавычки и пробелы.

В командной строке или командный файл пробелы и символы табуляции, разделяя аргументы и нельзя вокруг знака равенства. Если `string` содержит внедренные пробелы или символы табуляции, следует заключить саму строку или весь макрос в двойные кавычки (» «).

## <a name="see-also"></a>См. также

[Определение макроса NMAKE](../build/defining-an-nmake-macro.md)