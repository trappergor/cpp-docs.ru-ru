---
title: Класс accelerator_view_removed
ms.date: 03/27/2019
f1_keywords:
- accelerator_view_removed
- AMPRT/accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed::accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed::get_view_removed_reason
helpviewer_keywords:
- AMPRT/Concurrency::accelerator_view_removed::accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
ms.openlocfilehash: eddcf44966d197068113c5e7817dad37841261a3
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524843"
---
# <a name="acceleratorviewremoved-class"></a>Класс accelerator_view_removed

Исключение, возникающее при сбое основного вызова DirectX из-за механизм обнаружения и восстановления времени ожидания Windows.

## <a name="syntax"></a>Синтаксис

```
class accelerator_view_removed : public runtime_exception;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[Конструктор accelerator_view_removed](#ctor)|Инициализирует новый экземпляр класса `accelerator_view_removed`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[get_view_removed_reason](#get_view_removed_reason)|Возвращает код ошибки HRESULT, указывающее причину `accelerator_view` удаления объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Требования

**Заголовок:** amprt.h

**Пространство имен:** параллелизм

## <a name="ctor"></a> accelerator_view_removed

Инициализирует новый экземпляр класса [accelerator_view_removed](accelerator-view-removed-class.md) класса.

### <a name="syntax"></a>Синтаксис

```
explicit accelerator_view_removed(
    const char * message,
    HRESULT view_removed_reason ) throw();

explicit accelerator_view_removed(
    HRESULT view_removed_reason ) throw();
```

### <a name="parameters"></a>Параметры

*message*<br/>
Описание ошибки.

*view_removed_reason*<br/>
Код ошибки HRESULT, указывающее причину удаления `accelerator_view` объекта.

### <a name="return-value"></a>Возвращаемое значение

Новый экземпляр класса `accelerator_view_removed`.

## <a name="get_view_removed_reason"></a> get_view_removed_reason

Возвращает код ошибки HRESULT, указывающее причину `accelerator_view` удаления объекта.

### <a name="syntax"></a>Синтаксис

```
HRESULT get_view_removed_reason() const throw();
```

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
