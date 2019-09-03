---
title: Прагма runtime_checks
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
ms.openlocfilehash: a1c8e6cca27e157818e6ec80182f8fefa112daf1
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216619"
---
# <a name="runtime_checks-pragma"></a>Прагма runtime_checks

Отключает или восстанавливает параметры [/RTC](../build/reference/rtc-run-time-error-checks.md) .

## <a name="syntax"></a>Синтаксис

> **#pragma runtime_checks ("** [ *runtime_checks* ] **",** { **RESTORE** | **Off** } **)**

## <a name="remarks"></a>Примечания

Нельзя включить проверку времени выполнения, которая не была включена параметром компилятора. Например, если не указать `/RTCs` в командной строке, при указании параметра `#pragma runtime_checks( "s", restore)` не будет включена проверка кадра стека.

Директива pragma **runtime_checks** должна находиться за пределами функции и вступает в силу при первой функции, определенной после того, как будет показана директива pragma. Аргументы **restore** и **off** включают или отключают параметры, указанные в директиве **runtime_checks** .

Директива **runtime_checks** может содержать ноль или несколько параметров, приведенных в следующей таблице.

### <a name="parameters-of-the-runtime_checks-pragma"></a>Параметры директивы pragma runtime_checks

| Параметры | Тип проверки времени выполнения |
|--------------------|-----------------------------|
| **s** | Включает проверку (кадра) стека. |
| **c** | Сообщает, когда значение назначается меньшему типу данных, что приводит к потере данных. |
| **u** | Сообщает об использовании переменной перед ее определением. |

Эти параметры являются теми же, которые используются с `/RTC` параметром компилятора. Например:

```cpp
#pragma runtime_checks( "sc", restore )
```

Директива pragma **runtime_checks** с пустой строкой ( **""** ) представляет собой специальную форму директивы.

- При использовании параметра **Off** происходит включение проверок ошибок во время выполнения, перечисленных в приведенной выше таблице.

- При использовании параметра RESTORE он сбрасывает проверки ошибок во время выполнения до тех, которые были указаны с помощью `/RTC` параметра компилятора.

```cpp
#pragma runtime_checks( "", off )
/* runtime checks are off in this region */
#pragma runtime_checks( "", restore )
```

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
