---
title: Класс cancellation_token_registration
ms.date: 11/04/2016
f1_keywords:
- cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration
- PPLCANCELLATION_TOKEN/concurrency::cancellation_token_registration::cancellation_token_registration
helpviewer_keywords:
- cancellation_token_registration class
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
ms.openlocfilehash: c6ca8061181ec057110282fa297666235e898ff6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414195"
---
# <a name="cancellationtokenregistration-class"></a>Класс cancellation_token_registration

Класс `cancellation_token_registration` представляет уведомление обратного вызова из `cancellation_token`. При использовании метода `register` на `cancellation_token` для получения уведомления о времени выполнения отмены объект `cancellation_token_registration` возвращается как дескриптор для обратного вызова, чтобы вызывающий код мог запросить, чтобы определенный обратный вызов больше не выполнялся с помощью метода `deregister`.

## <a name="syntax"></a>Синтаксис

```
class cancellation_token_registration;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[cancellation_token_registration](#ctor)||
|[~ cancellation_token_registration деструктор](#dtor)||

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[operator!=](#operator_neq)||
|[оператор=](#operator_eq)||
|[operator==](#operator_eq_eq)||

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`cancellation_token_registration`

## <a name="requirements"></a>Требования

**Заголовок:** pplcancellation_token.h

**Пространство имен:** concurrency

##  <a name="dtor"></a> ~cancellation_token_registration

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
