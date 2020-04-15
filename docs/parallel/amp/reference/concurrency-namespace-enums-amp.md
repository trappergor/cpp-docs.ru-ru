---
title: Перечисления пространства имен Concurrency (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
ms.openlocfilehash: 2467db27ad36dfcda31dfb5bb45067ada5470d07
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376322"
---
# <a name="concurrency-namespace-enums-amp"></a>Перечисления пространства имен Concurrency (AMP)

|||
|-|-|
|[Перечисление access_type](#access_type)|[Перечисление queuing_mode](#queuing_mode)|

## <a name="access_type-enumeration"></a><a name="access_type"></a>access_type Инумерация

Тип enumeration используется для обозначения различных типов доступа к данным.

```cpp
enum access_type;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`access_type_auto`|Автоматически выбирайте лучшее `access_type` для акселератора.|
|`access_type_none`|Выделенный. Распределение доступно только на ускорителе, а не на процессоре.|
|`access_type_read`|Общий. Распределение доступно на ускорителе и читается на процессоре.|
|`access_type_read_write`|Общий. Распределение доступно на ускорителе и записывается на процессоре.|
|`access_type_write`|Общий. Распределение доступно на ускорителе и является читаемым и записным на процессоре.|

## <a name="queuing_mode-enumeration"></a><a name="queuing_mode"></a>queuing_mode Инумерация

Определяет режимы очередей, которые поддерживаются на ускорителе.

```cpp
enum queuing_mode;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`queuing_mode_immediate`|Режим очередей, который определяет, что любые команды, например, [parallel_for_each функция (C) AMP](concurrency-namespace-functions-amp.md#parallel_for_each), отправляются на соответствующее устройство ускорителя, как только они возвращаются к вызывающему абоненту.|
|`queuing_mode_automatic`|Режим очередей, который определяет, что команды стоят в очереди в командной очереди, соответствующей [accelerator_view](accelerator-view-class.md) объекту. Команды отправляются на устройство, когда [accelerator_view::флеш](accelerator-view-class.md#flush) вызывается.|

## <a name="see-also"></a>См. также раздел

[Пространство имен параллелизма (КЗ АМП)](concurrency-namespace-cpp-amp.md)
