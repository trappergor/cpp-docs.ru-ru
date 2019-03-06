---
title: Коды выхода из NMAKE
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, exit codes
- exit codes
ms.assetid: 75f6913c-1da5-4572-a2d3-8a4e058bed15
ms.openlocfilehash: 07a104d90d91a027864022d4c82412318eb5fe3d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413242"
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
