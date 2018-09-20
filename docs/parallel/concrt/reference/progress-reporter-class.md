---
title: Класс progress_reporter | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
dev_langs:
- C++
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8dfb224fb0c0f641e4b7ef8809268fa4fad58890
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438799"
---
# <a name="progressreporter-class"></a>Класс progress_reporter

Класс формирования отчетов о ходе выполнения позволяет формировать уведомления о ходе выполнения определенного типа. Каждый объект progress_reporter привязан к конкретному асинхронному действию или операции.

## <a name="syntax"></a>Синтаксис

```
template<typename _ProgressType>
class progress_reporter;
```

#### <a name="parameters"></a>Параметры

*_ProgressType*<br/>
О типе полезных данных каждого уведомления о ходе выполнения сообщается посредством формирования отчетов о ходе выполнения.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[progress_reporter](#ctor)||

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[отчет](#report)|Отправляет отчет о ходе выполнения в асинхронное действие или операцию, к которому привязано это средство формирования отчетов.|

## <a name="remarks"></a>Примечания

Этот тип доступен только для приложений среды выполнения Windows.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`progress_reporter`

## <a name="requirements"></a>Требования

**Заголовок:** ppltasks.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> progress_reporter

```
progress_reporter();
```

##  <a name="report"></a> отчет

Отправляет отчет о ходе выполнения в асинхронное действие или операцию, к которому привязано это средство формирования отчетов.

```
void report(const _ProgressType& val) const;
```

### <a name="parameters"></a>Параметры

*Val*<br/>
Полезные данные требуется сообщить посредством уведомления о ходе выполнения.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
