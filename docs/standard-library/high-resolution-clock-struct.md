---
title: Структура high_resolution_clock | Документация Майкрософт
ms.custom: ''
ms.date: 05/22/2018
ms.technology: cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::high_resolution_clock
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b00b20e7cea4fa24b37ad33d5536eb9844e6953
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269126"
---
# <a name="steadyclock-struct"></a>Структура steady_clock

Представляет *high_resolution* часов.

## <a name="syntax"></a>Синтаксис

```cpp
class high_resolution_clock
```

## <a name="members"></a>Участники

### <a name="typedefs"></a>Определения типов

|name|Описание|
|----------|-----------------|
|`duration`|Синоним для `nanoseconds`, определенный в \<chrono >.|
|`period`|Синоним для `nano`, определенный в \<соотношение >.|
|`rep`|Синоним для **long** **long**, тип, который используется для представления числа тактов часов при автономном создании экземпляра `duration`.|
|`time_point`|Синоним для `chrono::time_point<high_resolution_clock>`.|

## <a name="functions"></a>Функции

|||
|-|-|
|`now`|Возвращает текущее время как `time_point` значение.|

## <a name="constants"></a>Константы

|name|Описание|
|----------|-----------------|
|`is_steady`|Содержит **true**. Объект `high_resolution_clock` — *постоянный*.|
