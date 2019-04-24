---
title: Класс CEnumeratorAccessor
ms.date: 11/04/2016
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
- CEnumeratorAccessor.m_bIsParent
- ATL::CEnumeratorAccessor::m_bIsParent
- m_bIsParent
- ATL.CEnumeratorAccessor.m_bIsParent
- CEnumeratorAccessor::m_bIsParent
- ATL::CEnumeratorAccessor::m_nType
- CEnumeratorAccessor.m_nType
- CEnumeratorAccessor::m_nType
- ATL.CEnumeratorAccessor.m_nType
- m_nType
- ATL::CEnumeratorAccessor::m_szDescription
- CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szDescription
- ATL.CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szName
- ATL.CEnumeratorAccessor.m_szName
- m_szName
- ATL::CEnumeratorAccessor::m_szName
- CEnumeratorAccessor.m_szName
- CEnumeratorAccessor::m_szParseName
- ATL::CEnumeratorAccessor::m_szParseName
- m_szParseName
- CEnumeratorAccessor.m_szParseName
- ATL.CEnumeratorAccessor.m_szParseName
helpviewer_keywords:
- CEnumeratorAccessor class
- m_bIsParent
- m_nType
- m_szDescription
- m_szName
- m_szParseName
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
ms.openlocfilehash: e609b346bb4a0c2469c24e20540c646fa869ae26
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025167"
---
# <a name="cenumeratoraccessor-class"></a>Класс CEnumeratorAccessor

Используемые [CEnumerator](../../data/oledb/cenumerator-class.md) доступ к данным из перечислитель набора строк.

## <a name="syntax"></a>Синтаксис

```cpp
class CEnumeratorAccessor
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_bIsParent](#bisparent)|Переменная, указывающее, является ли перечислитель перечислитель родительского, если строка не содержит перечислителя.|
|[m_nType](#ntype)|Переменная, указывающее, является ли строка описывает источник данных или перечислителя.|
|[m_szDescription](#szdescription)|Описание источника данных или перечислителя.|
|[m_szName](#szname)|Имя источника данных или перечислителя.|
|[m_szParseName](#szparsename)|Строка, передаваемая для [IParseDisplayName](/windows/desktop/api/oleidl/nn-oleidl-iparsedisplayname) для получения моникера для источника данных или перечислителя.|

## <a name="remarks"></a>Примечания

Этот набор строк состоит из источников данных и перечислители, отображается в текущий перечислитель.

## <a name="bisparent"></a> CEnumeratorAccessor::m_bIsParent

Переменная, указывающее, является ли перечислитель перечислитель родительского, если строка не содержит перечислителя.

### <a name="syntax"></a>Синтаксис

```cpp
VARIANT_BOOL m_bIsParent;
```

### <a name="remarks"></a>Примечания

См. в разделе [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) в *Справочник программиста OLE DB по* Дополнительные сведения.

## <a name="ntype"></a> CEnumeratorAccessor::m_nType

Переменная, указывающее, является ли строка описывает источник данных или перечислителя.

### <a name="syntax"></a>Синтаксис

```cpp
USHORT m_nType;
```

### <a name="remarks"></a>Примечания

См. в разделе [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) в *Справочник программиста OLE DB по* Дополнительные сведения.

## <a name="szdescription"></a> CEnumeratorAccessor::m_szDescription

Описание источника данных или перечислителя.

### <a name="syntax"></a>Синтаксис

```cpp
WCHAR m_szDescription[129];
```

### <a name="remarks"></a>Примечания

См. в разделе [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) в *Справочник программиста OLE DB по* Дополнительные сведения.

## <a name="szname"></a> CEnumeratorAccessor::m_szName

Имя источника данных или перечислителя.

### <a name="syntax"></a>Синтаксис

```cpp
WCHAR m_szName[129];
```

### <a name="remarks"></a>Примечания

См. в разделе [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) в *Справочник программиста OLE DB по* Дополнительные сведения.

## <a name="szparsename"></a> CEnumeratorAccessor::m_szParseName

Строка, передаваемая для [IParseDisplayName](/windows/desktop/api/oleidl/nn-oleidl-iparsedisplayname) для получения моникера для источника данных или перечислителя.

### <a name="syntax"></a>Синтаксис

```cpp
WCHAR m_szParseName[129];
```

### <a name="remarks"></a>Примечания

См. в разделе [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) в *Справочник программиста OLE DB по* Дополнительные сведения.

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)