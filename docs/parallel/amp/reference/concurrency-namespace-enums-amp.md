---
title: Перечисления пространства имен Concurrency (AMP) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
dev_langs:
- C++
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58d70b995642eaca3dbefd75383e6d6bf06f2c62
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082441"
---
# <a name="concurrency-namespace-enums-amp"></a>Перечисления пространства имен Concurrency (AMP)

|||
|-|-|
|[Перечисление access_type](#access_type)|[Перечисление queuing_mode](#queuing_mode)|

##  <a name="access_type"></a>  Перечисление access_type

Тип перечисления, используемый для обозначения различных типов доступа к данным.

```
enum access_type;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`access_type_auto`|Автоматически выбирает наилучший `access_type` для сочетания клавиш.|
|`access_type_none`|Выделенные. Выделение доступно только в сочетании клавиш и недоступно на ЦП.|
|`access_type_read`|Общий доступ. Выделение доступно в сочетании клавиш и читаемо на ЦП.|
|`access_type_read_write`|Общий доступ. Выделение доступно в сочетании клавиш и записать на ЦП.|
|`access_type_write`|Общий доступ. Выделение доступно в сочетании клавиш и для чтения и на ЦП.|

##  <a name="queuing_mode"></a>  Перечисление queuing_mode

Определяет режимы организации очереди, которые поддерживаются в сочетании клавиш.

```
enum queuing_mode;
```

### <a name="values"></a>Значения

|Имя|Описание|
|----------|-----------------|
|`queuing_mode_immediate`|Режим организации очереди, указывающий, что любые команды, например, [parallel_for_each функции (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each), отправляемые в соответствующий ускоритель, как только они возвращаются вызывающему объекту.|
|`queuing_mode_automatic`|Режим организации очереди, которое указывает, что команды будут ставиться в очередь, которая соответствует [accelerator_view](accelerator-view-class.md) объекта. Команды отправляются на устройство при [accelerator_view::flush](accelerator-view-class.md#flush) вызывается.|

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
