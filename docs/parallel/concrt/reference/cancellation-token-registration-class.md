---
title: Класс cancellation_token_registration | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration::cancellation_token_registration
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1622dc78e0629bb90a6b646e4910cfb362be721e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398434"
---
# <a name="cancellationtokenregistration-class"></a>Класс cancellation_token_registration

Класс `cancellation_token_registration` представляет уведомление обратного вызова из `cancellation_token`. При использовании метода `register` на `cancellation_token` для получения уведомления о времени выполнения отмены объект `cancellation_token_registration` возвращается как дескриптор для обратного вызова, чтобы вызывающий код мог запросить, чтобы определенный обратный вызов больше не выполнялся с помощью метода `deregister`.

## <a name="syntax"></a>Синтаксис

```
class cancellation_token_registration;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[cancellation_token_registration](#ctor)||
|[~ cancellation_token_registration деструктор](#dtor)||

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор!=](#operator_neq)||
|[оператор=](#operator_eq)||
|[оператор==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`cancellation_token_registration`

## <a name="requirements"></a>Требования

**Заголовок:** pplcancellation_token.h

**Пространство имен:** concurrency

##  <a name="dtor"></a> ~ cancellation_token_registration

```
~cancellation_token_registration();
```

##  <a name="ctor"></a> cancellation_token_registration

```
cancellation_token_registration();

cancellation_token_registration(const cancellation_token_registration& _Src);

cancellation_token_registration(cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
`cancellation_token_registration` Для копирования или перемещения.

##  <a name="operator_neq"></a> оператор! =

```
bool operator!= (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Сравниваемый шаблон `cancellation_token_registration`.

### <a name="return-value"></a>Возвращаемое значение

##  <a name="operator_eq"></a> оператор =

```
cancellation_token_registration& operator= (const cancellation_token_registration& _Src);

cancellation_token_registration& operator= (cancellation_token_registration&& _Src);
```

### <a name="parameters"></a>Параметры

*_Src*<br/>
`cancellation_token_registration` Для назначения.

### <a name="return-value"></a>Возвращаемое значение

##  <a name="operator_eq_eq"></a> оператор ==

```
bool operator== (const cancellation_token_registration& _Rhs) const;
```

### <a name="parameters"></a>Параметры

*_Rhs*<br/>
Сравниваемый шаблон `cancellation_token_registration`.

### <a name="return-value"></a>Возвращаемое значение

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
