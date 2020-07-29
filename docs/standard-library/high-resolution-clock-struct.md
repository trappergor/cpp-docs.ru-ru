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
ms.openlocfilehash: 850d5e3a5434aa44e23a7f74aeb9c306ab6c0a8e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203212"
---
# <a name="steady_clock-struct"></a>Структура steady_clock

Представляет *high_resolution* часы.

## <a name="syntax"></a>Синтаксис

```cpp
class high_resolution_clock
```

## <a name="members"></a>Участники

### <a name="typedefs"></a>Определения типов

|Имя|Описание|
|----------|-----------------|
|`duration`|Синоним `nanoseconds` , определенный в \<chrono> .|
|`period`|Синоним `nano` , определенный в \<ratio> .|
|`rep`|Синоним **`long long`** типа, который используется для представления количества тактов часов в автономном экземпляре `duration` .|
|`time_point`|Синоним для `chrono::time_point<high_resolution_clock>`.|

## <a name="functions"></a>Функции

|||
|-|-|
|`now`|Возвращает текущее время в виде `time_point` значения.|

## <a name="constants"></a>Константы

|Имя|Описание|
|----------|-----------------|
|`is_steady`|Содержит **`true`** . Объект `high_resolution_clock` — *постоянный*.|
