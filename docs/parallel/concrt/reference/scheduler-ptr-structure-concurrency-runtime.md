---
title: структура scheduler_ptr
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: 60d71a26e5dffcadfb900ef15c26a6d9dc6d6f8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358773"
---
# <a name="scheduler_ptr-structure"></a>структура scheduler_ptr

Представляет указатель на планировщик. Этот класс существует, чтобы позволить спецификации общей жизни, используя shared_ptr или просто ссылку с помощью сырья указатель.

## <a name="syntax"></a>Синтаксис

```cpp
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
|[scheduler_ptr::оператор бул](#operator_bool)|Проверьте, является ли указатель планировщика отличным от null|
|[scheduler_ptr::оператор-&gt;](#operator_ptr)|Поведение, как у указателя|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`scheduler_ptr`

## <a name="requirements"></a>Требования

**Заголовок:** pplinterface.h

**Название:** параллелизм

## <a name="scheduler_ptrget-method"></a><a name="get"></a>scheduler_ptr::Получить метод

Возвращает необработанный указатель планировщику.

```cpp
scheduler_interface* get() const;
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="scheduler_ptroperator-bool"></a><a name="operator_bool"></a>scheduler_ptr::оператор бул

Проверяет, является ли указатель планировщика ненулевым.

```cpp
operator bool() const;
```

## <a name="scheduler_ptroperator-gt"></a><a name="operator_ptr"></a>scheduler_ptr::оператор-&gt;

Ведет себя как указатель.

```cpp
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="scheduler_ptrscheduler_ptr-constructor"></a><a name="ctor"></a>scheduler_ptr:::scheduler_ptr Конструктор

Создает указатель планировщика от shared_ptr к планировщику.

```cpp
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>Параметры

*Планировщик*<br/>
Планировщик для преобразования.

*pПланировщик*<br/>
Указатель планировщика для преобразования.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
