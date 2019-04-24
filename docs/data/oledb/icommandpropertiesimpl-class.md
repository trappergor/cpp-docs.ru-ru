---
title: Класс ICommandPropertiesImpl
ms.date: 11/04/2016
f1_keywords:
- ICommandPropertiesImpl
- ATL.ICommandPropertiesImpl
- ATL::ICommandPropertiesImpl
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- GetProperties
- ICommandPropertiesImpl.SetProperties
- ICommandPropertiesImpl::SetProperties
- SetProperties
helpviewer_keywords:
- ICommandPropertiesImpl class
- GetProperties method
- SetProperties method
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
ms.openlocfilehash: 1250f1c5c5094a0ca8348f325260e6079afe2baa
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034106"
---
# <a name="icommandpropertiesimpl-class"></a>Класс ICommandPropertiesImpl

Предоставляет реализацию [ICommandProperties](/previous-versions/windows/desktop/ms723044(v=vs.85)) интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class PropClass = T>
class ATL_NO_VTABLE ICommandPropertiesImpl
   : public ICommandProperties, public CUtlProps<PropClass>
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс, производный от

*PropClass*<br/>
Класс свойств.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="interface-methods"></a>Методы интерфейса

|||
|-|-|
|[GetProperties](#getproperties)|Возвращает список свойств в группе свойств набора строк, в настоящее время запрашиваются для набора строк.|
|[SetProperties](#setproperties)|Задает свойства в группе свойств набора строк.|

## <a name="remarks"></a>Примечания

Это обязательно на команды. Реализация предоставляется с определением статическую функцию [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) макрос.

## <a name="getproperties"></a> ICommandPropertiesImpl::GetProperties

Возвращает все наборы запрошенного свойства, с помощью команды сопоставление свойств.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,
   const DBPROPIDSET rgPropertyIDSets[],
   ULONG * pcPropertySets,
   DBPROPSET ** prgPropertySets);
```

#### <a name="parameters"></a>Параметры

См. в разделе [ICommandProperties::GetProperties](/previous-versions/windows/desktop/ms723119(v=vs.85)) в *справочнике программиста OLE DB*.

### <a name="remarks"></a>Примечания

См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).

## <a name="setproperties"></a> ICommandPropertiesImpl::SetProperties

Задает свойства для объекта команды.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD(SetProperties)(ULONG cPropertySets,
   DBPROPSET rgPropertySets[]);
```

#### <a name="parameters"></a>Параметры

См. в разделе [ICommandProperties::SetProperties](/previous-versions/windows/desktop/ms711497(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)