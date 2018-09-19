---
title: Ошибка BSCMAKE BK1503 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1503
dev_langs:
- C++
helpviewer_keywords:
- BK1503
ms.assetid: e6582344-b91e-486f-baf3-4f9028d83c3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16bf228804cb24f4fe7a2428dc581116d4cec91d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064676"
---
# <a name="bscmake-error-bk1503"></a>Ошибка BSCMAKE BK1503

не удается записать файл «имя_файла» [: причина]

BSCMAKE совмещает SBR-файлы, созданные во время компиляции в одной базе данных браузера. Если базы данных превышает 64 МБ, или если количество входных SBR-файлов превышает 4092, эта ошибка, будет использовано.

Если проблема вызвана превышает 4092 SBR-файлов, необходимо уменьшить количество входных файлов. В Visual Studio это можно добиться путем [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) всего проекта, то проверку на основе файлы.

Если проблема вызвана BSC-файла, размер которых превышает 64 МБ, уменьшение количества SBR-файлы в качестве входных данных будет уменьшить размер получившийся BSC-файл. Кроме того объем данных просмотра можно уменьшить /Em (исключить символы расширения макросов), /El (исключить локальные переменные) и /Es (исключить системные файлы).

## <a name="see-also"></a>См. также

[Параметры BSCMAKE](../../build/reference/bscmake-options.md)