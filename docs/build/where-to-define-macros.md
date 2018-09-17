---
title: Где следует определять макросы | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29a2899d7dba0b34c0ac3319c253c8056912d883
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713821"
---
# <a name="where-to-define-macros"></a>Где следует определять макросы

Макросы определяются в командную строку, командный файл, файл makefile или файле Tools.ini.

В файле makefile или файле Tools.ini каждое определение макроса должны располагаться на отдельной строке и не может начинаться с пробела или табуляции. Игнорируются пробелы или знаки табуляции вокруг знака равенства. Все [строка символов](../build/defining-an-nmake-macro.md) являются литералами, в том числе заключающие кавычки и пробелы.

В командной строке или командный файл пробелы и символы табуляции, разделяя аргументы и нельзя вокруг знака равенства. Если `string` содержит внедренные пробелы или символы табуляции, следует заключить саму строку или весь макрос в двойные кавычки (» «).

## <a name="see-also"></a>См. также

[Определение макроса NMAKE](../build/defining-an-nmake-macro.md)