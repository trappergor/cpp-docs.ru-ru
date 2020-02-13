---
title: Класс CComPtr
description: Справочное руководство по классу библиотеки Microsoft C++ Active Template Library (ATL) CComPtr.
ms.date: 02/07/2020
f1_keywords:
- CComPtr
- ATLBASE/ATL::CComPtr
- ATLBASE/ATL::CComPtr::CComPtr
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
ms.openlocfilehash: 74a12b460f55a782fa2747b02f7d00287786fae6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127410"
---
# <a name="ccomptr-class"></a>Класс CComPtr

Класс интеллектуального указателя для управления указателями на интерфейс COM.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
class CComPtr
```

### <a name="parameters"></a>Параметры

*T*<br/>
COM-интерфейс, указывающий тип сохраняемого указателя.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[CComPtr:: CComPtr](#ccomptr)|Конструктор.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[CComPtr:: operator =](#operator_eq)|Присваивает указатель на указатель члена.|

## <a name="remarks"></a>Remarks

ATL использует `CComPtr` и [CComQIPtr](../../atl/reference/ccomqiptr-class.md) для управления указателями на интерфейс COM. Оба являются производными от [ккомптрбасе](../../atl/reference/ccomptrbase-class.md)и выполняют автоматический подсчет ссылок.

Классы `CComPtr` и [CComQIPtr](../../atl/reference/ccomqiptr-class.md) могут помочь устранить утечки памяти, выполнив автоматический подсчет ссылок.  Следующие функции выполняют одни и те же логические операции. Однако вторая версия может быть менее подвержена ошибкам, поскольку она использует класс `CComPtr`:

[!code-cpp[NVC_ATL_Utilities#130](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]

[!code-cpp[NVC_ATL_Utilities#131](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]

В отладочных сборках свяжите атлсд. lib с трассировкой кода.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[ккомптрбасе](../../atl/reference/ccomptrbase-class.md)

`CComPtr`

## <a name="requirements"></a>Требования

**Заголовок:** atlbase. h

## <a name="ccomptr"></a>CComPtr:: CComPtr

Конструктор.

```cpp
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```

### <a name="parameters"></a>Параметры

*LP*<br/>
Используется для инициализации указателя интерфейса.

*T*<br/>
COM-интерфейс.

### <a name="remarks"></a>Remarks

Конструкторы, которые принимают вызов аргумента `AddRef` в *LP*, если он не является пустым указателем. Собственный объект, не принадлежащий null, получает `Release` вызове уничтожения объекта CComPtr или если новый объект назначается объекту CComPtr.

## <a name="operator_eq"></a>CComPtr:: operator =

Оператор присвоения.

```cpp
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на обновленный объект `CComPtr`

### <a name="remarks"></a>Remarks

Эта операция AddRef новый объект и освобождает существующий объект, если он существует.

## <a name="see-also"></a>См. также раздел

[CComPtr:: CComPtr](#ccomptr)<br/>
[CComQIPtr:: CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
