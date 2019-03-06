---
title: Класс IColumnsInfoImpl
ms.date: 11/04/2016
f1_keywords:
- ATL.IColumnsInfoImpl<T>
- ATL::IColumnsInfoImpl
- IColumnsInfoImpl
- ATL.IColumnsInfoImpl
- ATL::IColumnsInfoImpl<T>
- GetColumnInfo
- ATL::IColumnsInfoImpl::GetColumnInfo
- ATL.IColumnsInfoImpl.GetColumnInfo
- ATL::IColumnsInfoImpl<T>::GetColumnInfo
- IColumnsInfoImpl::GetColumnInfo
- IColumnsInfoImpl<T>::GetColumnInfo
- IColumnsInfoImpl.GetColumnInfo
- IColumnsInfoImpl<T>::MapColumnIDs
- MapColumnIDs
- ATL::IColumnsInfoImpl::MapColumnIDs
- IColumnsInfoImpl.MapColumnIDs
- ATL::IColumnsInfoImpl<T>::MapColumnIDs
- IColumnsInfoImpl::MapColumnIDs
- ATL.IColumnsInfoImpl<T>.MapColumnIDs
- ATL.IColumnsInfoImpl.MapColumnIDs
helpviewer_keywords:
- IColumnsInfoImpl class
- GetColumnInfo method
- MapColumnIDs method
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
ms.openlocfilehash: 802c105e7795cdce604e72983f4fda549abcd5fb
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57418273"
---
# <a name="icolumnsinfoimpl-class"></a>Класс IColumnsInfoImpl

Предоставляет реализацию [IColumnsInfo](/previous-versions/windows/desktop/ms724541(v=vs.85)) интерфейс.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
class ATL_NO_VTABLE IColumnsInfoImpl :
   public IColumnsInfo, 
   public CDBIDOps
```

### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IColumnsInfoImpl`.

## <a name="requirements"></a>Требования

**Заголовок:** atldb.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[GetColumnInfo](#getcolumninfo)|Возвращает метаданные столбца, требуемые большинством объектов-получателей.|
|[MapColumnIDs](#mapcolumnids)|Возвращает массив порядковых номеров столбцов в наборе строк, которые идентифицируются по указанному столбцу идентификаторов.|

## <a name="remarks"></a>Примечания

Обязательный интерфейс для наборов строк и команд. Для изменения поведения вашего поставщика `IColumnsInfo` реализации, необходимо изменить сопоставление столбцов поставщика.

## <a name="getcolumninfo"></a> IColumnsInfoImpl::GetColumnInfo

Возвращает метаданные столбца, требуемые большинством объектов-получателей.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (GetColumnInfo)(DBORDINAL* pcColumns,
   DBCOLUMNINFO** prgInfo,
   OLECHAR** ppStringsBuffer);
```

#### <a name="parameters"></a>Параметры

См. в разделе [IColumnsInfo::GetColumnInfo](/previous-versions/windows/desktop/ms722704\(v=vs.85\)) в *справочнике программиста OLE DB*.

## <a name="mapcolumnids"></a> IColumnsInfoImpl::MapColumnIDs

Возвращает массив порядковых номеров столбцов в наборе строк, которые идентифицируются по указанному столбцу идентификаторов.

### <a name="syntax"></a>Синтаксис

```cpp
STDMETHOD (MapColumnIDs)(DBORDINAL cColumnIDs,
   const DBID rgColumnIDs[],
   DBORDINAL rgColumns[]);
```

#### <a name="parameters"></a>Параметры

См. в разделе [IColumnsInfo::MapColumnIDs](/previous-versions/windows/desktop/ms714200(v=vs.85)) в *справочнике программиста OLE DB*.

## <a name="see-also"></a>См. также

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)