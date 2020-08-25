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
ms.openlocfilehash: a79cb91a6b0e6ca633540fd37f7a0e1ece53b712
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845791"
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

|Имя|Описание|
|-|-|
|`now`|Возвращает текущее время в виде `time_point` значения.|

## <a name="constants"></a>Константы

|Имя|Описание|
|----------|-----------------|
|`is_steady`|Содержит **`true`** . Объект `high_resolution_clock` — *постоянный*.|
