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
ms.openlocfilehash: 341cae04742d72fdcc7483e74977bf413854df82
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039655"
---
# <a name="high_resolution_clock-struct"></a>Структура high_resolution_clock

Представляет *high_resolution* часы.

## <a name="syntax"></a>Синтаксис

```cpp
class high_resolution_clock
```

## <a name="members"></a>Участники

### <a name="typedefs"></a>Определения типов

|name|Описание|
|----------|-----------------|
|`duration`|Синоним `nanoseconds` , определенный в \<chrono> .|
|`period`|Синоним `nano` , определенный в \<ratio> .|
|`rep`|Синоним **`long long`** типа, который используется для представления количества тактов часов в автономном экземпляре `duration` .|
|`time_point`|Синоним для `chrono::time_point<high_resolution_clock>`.|

## <a name="functions"></a>Функции

|name|Описание|
|-|-|
|`now`|Возвращает текущее время в виде `time_point` значения.|

## <a name="constants"></a>Константы

|name|Описание|
|----------|-----------------|
|`is_steady`|Содержит **`true`** . Объект `high_resolution_clock` — *постоянный*.|
