---
title: Где следует определять макросы
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: dc03644adea4619b3eabe33c481d71f704a9f410
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62316370"
---
# <a name="where-to-define-macros"></a>Где следует определять макросы

Макросы определяются в командную строку, командный файл, файл makefile или файле Tools.ini.

В файле makefile или файле Tools.ini каждое определение макроса должны располагаться на отдельной строке и не может начинаться с пробела или табуляции. Игнорируются пробелы или знаки табуляции вокруг знака равенства. Все [строка символов](defining-an-nmake-macro.md) являются литералами, в том числе заключающие кавычки и пробелы.

В командной строке или командный файл пробелы и символы табуляции, разделяя аргументы и нельзя вокруг знака равенства. Если `string` содержит внедренные пробелы или символы табуляции, следует заключить саму строку или весь макрос в двойные кавычки (» «).

## <a name="see-also"></a>См. также

[Определение макроса NMAKE](defining-an-nmake-macro.md)
