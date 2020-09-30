---
title: Класс ISessionPropertiesImpl
ms.date: 11/04/2016
f1_keywords:
- ISessionPropertiesImpl
- ISessionPropertiesImpl::GetProperties
- ISessionPropertiesImpl.GetProperties
- ISessionPropertiesImpl.SetProperties
- ISessionPropertiesImpl::SetProperties
helpviewer_keywords:
- ISessionPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
ms.openlocfilehash: d664f32226498326ffb092f1d3248fbdbf614d50
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509765"
---
# <a name="isessionpropertiesimpl-class"></a>Класс ISessionPropertiesImpl

Предоставляет реализацию интерфейса [исессионпропертиес](/previous-versions/windows/desktop/ms713721(v=vs.85)) .

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ISessionPropertiesImpl :
   public ISessionProperties,
   public CUtlProps<PropClass>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от `ISessionPropertiesImpl` .

*пропкласс*<br/>
Определяемый пользователем класс свойств, который по умолчанию имеет значение *T*.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Элементы

### <a name="interface-methods"></a>Методы интерфейса

| Название | Описание |
|-|-|
|[GetProperties](#getproperties)|Возвращает список свойств в группе свойств сеанса, которые в настоящее время заданы в сеансе.|
|[SetProperties](#setproperties)|Задает свойства в группе свойств сеанса.|

## <a name="remarks"></a>Remarks

Обязательный интерфейс в сеансах. Этот класс реализует свойства сеанса путем вызова статической функции, определенной в [сопоставлении набора свойств](./macros-for-ole-db-provider-templates.md#begin_propset_map). Схема набора свойств должна быть указана в классе сеанса.

## <a name="isessionpropertiesimplgetproperties"></a><a name="getproperties"></a> Свойства ISessionPropertiesImpl:: Properties

Возвращает список свойств в `DBPROPSET_SESSION` группе свойств, установленных в данный момент в сеансе.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetProperties)(ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>Параметры

См. раздел [исессионпропертиес:: Properties](/previous-versions/windows/desktop/ms723643(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="isessionpropertiesimplsetproperties"></a><a name="setproperties"></a> ISessionPropertiesImpl:: SetProperties

Задает свойства в `DBPROPSET_SESSION` группе свойств.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Параметры

См. раздел [исессионпропертиес:: SetProperties](/previous-versions/windows/desktop/ms714405(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также раздел

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)
