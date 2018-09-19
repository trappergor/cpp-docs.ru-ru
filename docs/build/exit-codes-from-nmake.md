---
title: Коды выхода из NMAKE | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3b5a593e38efb5230630ed01e65f4bfb1f2ba92a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722622"
---
# <a name="exit-codes-from-nmake"></a>Коды выхода из NMAKE

NMAKE возвращает следующие коды выхода:

|Код|Значение|
|----------|-------------|
|0|Нет ошибок (возможно предупреждение)|
|1|Неполные сборки (выдан только при использовании /K)|
|2|Ошибка программы, возможно из-за одно из следующих:|
||-Синтаксическая ошибка в файле makefile|
||Ошибка или код выхода из команды|
||-Прервано пользователем|
|4|Системная ошибка — Недостаточно памяти|
|255|Целевой объект не актуален (выдан только при использовании/q)|

## <a name="see-also"></a>См. также

[Запуск программы NMAKE](../build/running-nmake.md)