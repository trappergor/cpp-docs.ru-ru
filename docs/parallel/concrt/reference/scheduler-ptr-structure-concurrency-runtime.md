---
title: Структура scheduler_ptr
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: 0da45fa18d12b3f1c93df6b8c8736ed1bfb58ade
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51525009"
---
# <a name="schedulerptr-structure"></a>Структура scheduler_ptr

Представляет указатель на планировщик. Этот класс существует в том, чтобы разрешить в спецификации общего времени жизни путем применения shared_ptr или простой ссылки с помощью необработанного указателя.

## <a name="syntax"></a>Синтаксис

```
struct scheduler_ptr;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[scheduler_ptr::scheduler_ptr](#ctor)|Перегружен. Создает указатель планировщика из shared_ptr планировщику|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[scheduler_ptr::get](#get)|Возвращает необработанный указатель планировщику|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[scheduler_ptr::operator bool](#operator_bool)|Проверьте, является ли указатель планировщика отличным от null|
|[scheduler_ptr::operator-&gt;](#operator_ptr)|Поведение, как у указателя|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`scheduler_ptr`

## <a name="requirements"></a>Требования

**Заголовок:** pplinterface.h

**Пространство имен:** concurrency

##  <a name="get"></a>  Метод scheduler_ptr::Get

Возвращает необработанный указатель планировщику.

```
scheduler_interface* get() const;
```

### <a name="return-value"></a>Возвращаемое значение

##  <a name="operator_bool"></a>  scheduler_ptr::operator bool

Проверяет, является ли указатель планировщика, отличных от null.

```
operator bool() const;
```

##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;

Действует как указатель.

```
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

##  <a name="ctor"></a>  Конструктор scheduler_ptr::scheduler_ptr

Создает указатель планировщика из shared_ptr планировщику.

```
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>Параметры

*scheduler*<br/>
Планировщик для преобразования.

*pScheduler*<br/>
Указатель планировщика для преобразования.

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
