---
title: Класс CComObjectStack | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
dev_langs:
- C++
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 277951a5425a75c9769c5a2c4104421303f677c2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065345"
---
# <a name="ccomobjectstack-class"></a>Класс CComObjectStack

Этот класс создает временный объект COM и предоставляет его с базовой реализацией `IUnknown`.

## <a name="syntax"></a>Синтаксис

```
template <class  Base>
class CComObjectStack : public Base
```

#### <a name="parameters"></a>Параметры

*Base*<br/>
Ваш класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), а также как и из любого другого интерфейса, которые должны поддерживаться в объекте.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|Конструктор.|
|[CComObjectStack:: ~ CComObjectStack](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CComObjectStack::AddRef](#addref)|Возвращает ноль. В режиме отладки, вызывает `_ASSERTE`.|
|[CComObjectStack::QueryInterface](#queryinterface)|Возвращает значение E_NOINTERFACE. В режиме отладки, вызывает `_ASSERTE`.|
|[CComObjectStack::Release](#release)|Возвращает ноль. В режиме отладки, вызывает `_ASSERTE`. ~|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|Содержит значение HRESULT, возвращенное во время создания `CComObjectStack` объекта.|

## <a name="remarks"></a>Примечания

`CComObjectStack` используется для создания временных объектов COM и обеспечивают базовую реализацию объекта `IUnknown`. Как правило объект используется как локальная переменная в одной функции (которая помещается в стек). Так как объект уничтожается после завершения работы функции, подсчет ссылок не выполняется для повышения эффективности.

Приведенный ниже показано, как создать объект COM, используемый внутри функции:

[!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]

Временный объект `Tempobj` помещается в стек и автоматически исчезает, когда функция выполнена.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Base`

`CComObjectStack`

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="addref"></a>  CComObjectStack::AddRef

Возвращает ноль.

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ноль.

### <a name="remarks"></a>Примечания

В режиме отладки, вызывает `_ASSERTE`.

##  <a name="ccomobjectstack"></a>  CComObjectStack::CComObjectStack

Конструктор.

```
CComObjectStack(void* = NULL);
```

### <a name="remarks"></a>Примечания

Вызовы `FinalConstruct` и затем задает [m_hResFinalConstruct](#m_hresfinalconstruct) в значение HRESULT, возвращенное `FinalConstruct`. Если не производного базового класса из [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), необходимо создать собственные `FinalConstruct` метод. Деструктор вызывает `FinalRelease`.

##  <a name="dtor"></a>  CComObjectStack:: ~ CComObjectStack

Деструктор

```
CComObjectStack();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы и вызовы [FinalRelease](ccomobjectrootex-class.md#finalrelease).

##  <a name="m_hresfinalconstruct"></a>  CComObjectStack::m_hResFinalConstruct

Содержит значение HRESULT, возвращенное из вызова метода `FinalConstruct` во время создания `CComObjectStack` объекта.

```
HRESULT    m_hResFinalConstruct;
```

##  <a name="queryinterface"></a>  CComObjectStack::QueryInterface

Возвращает значение E_NOINTERFACE.

```
HRESULT    QueryInterface(REFIID, void**);
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение E_NOINTERFACE.

### <a name="remarks"></a>Примечания

В режиме отладки, вызывает `_ASSERTE`.

##  <a name="release"></a>  CComObjectStack::Release

Возвращает ноль.

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ноль.

### <a name="remarks"></a>Примечания

В режиме отладки, вызывает `_ASSERTE`.

## <a name="see-also"></a>См. также

[Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)<br/>
[Класс CComObject](../../atl/reference/ccomobject-class.md)<br/>
[Класс CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
