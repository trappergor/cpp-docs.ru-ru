---
title: runtime_checks
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
ms.openlocfilehash: 38df7ccc384830bb547c11e1a3d5458a1298574c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547372"
---
# <a name="runtimechecks"></a>runtime_checks
Отключает или восстанавливает параметры [/RTC](../build/reference/rtc-run-time-error-checks.md) .

## <a name="syntax"></a>Синтаксис

```
#pragma runtime_checks( "[runtime_checks]", {restore | off} )
```

## <a name="remarks"></a>Примечания

Невозможно включить проверку времени выполнения, не включенную с параметром компилятора. Например, если вы не укажете `/RTCs`, указав `#pragma runtime_checks( "s", restore)` не будет включению проверки кадра стека.

Директива pragma **runtime_checks** должна находиться за пределами функции; она вступает в силу в первой функции, определенной после этой директивы. Аргументы *restore* и *off* включают или отключают параметры, указанные в директиве **runtime_checks** .

Директива **runtime_checks** может содержать ноль или несколько параметров, приведенных в следующей таблице.

### <a name="parameters-of-the-runtimechecks-pragma"></a>Параметры директивы pragma runtime_checks

|Параметры|Тип проверки времени выполнения|
|--------------------|-----------------------------|
|*s*|Включает проверку (кадра) стека.|
|*c*|Сообщает, когда значение назначается меньшему типу данных, что приводит к потере данных.|
|*u*|Сообщает о том, что переменная используется до ее определения.|

Это же буквы используются с `/RTC` параметр компилятора. Пример:

```
#pragma runtime_checks( "sc", restore )
```

Директива pragma **runtime_checks** с пустой строкой (**""**) представляет собой специальную форму директивы.

- При использовании параметра *off* она отключает проверки ошибок во время выполнения, перечисленные в таблице выше.

- При использовании *восстановить* параметр, она сбрасывает проверки ошибок во время выполнения до указанных с `/RTC` параметр компилятора.

```
#pragma runtime_checks( "", off )
.
.
.
#pragma runtime_checks( "", restore )
```

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)