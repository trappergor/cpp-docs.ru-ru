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
- ATL::CEnumeratorAccessor::m_szDescription
- CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szDescription
- ATL.CEnumeratorAccessor.m_szDescription
- CEnumeratorAccessor::m_szName
- ATL.CEnumeratorAccessor.m_szName
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
ms.openlocfilehash: d85f630a01ab7e2a07035a8a304a56be91eca8a9
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545633"
---
# <a name="cenumeratoraccessor-class"></a>Класс CEnumeratorAccessor

Используется [CEnumerator](../../data/oledb/cenumerator-class.md) для доступа к данным из набора строк перечислителя.

## <a name="syntax"></a>Синтаксис

```cpp
class CEnumeratorAccessor
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Члены

### <a name="data-members"></a>Элементы данных

|||
|-|-|
|[m_bIsParent](#bisparent)|Переменная, указывающая, является ли перечислитель родительским перечислителем, если строка является перечислителем.|
|[m_nType](#ntype)|Переменная, указывающая, описывает ли строка источник данных или перечислитель.|
|[m_szDescription](#szdescription)|Описание источника данных или перечислителя.|
|[m_szName](#szname)|Имя источника данных или перечислителя.|
|[m_szParseName](#szparsename)|Строка для передачи в [ипарседисплайнаме](/windows/win32/api/oleidl/nn-oleidl-iparsedisplayname) для получения моникера для источника данных или перечислителя.|

## <a name="remarks"></a>Примечания

Этот набор строк состоит из источников данных и перечислителей, видимых из текущего перечислителя.

## <a name="cenumeratoraccessorm_bisparent"></a><a name="bisparent"></a>CEnumeratorAccessor:: m_bIsParent

Переменная, указывающая, является ли перечислитель родительским перечислителем, если строка является перечислителем.

### <a name="syntax"></a>Синтаксис

```cpp
VARIANT_BOOL m_bIsParent;
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) в *справочнике программиста OLE DB* .

## <a name="cenumeratoraccessorm_ntype"></a><a name="ntype"></a>CEnumeratorAccessor:: m_nType

Переменная, указывающая, описывает ли строка источник данных или перечислитель.

### <a name="syntax"></a>Синтаксис

```cpp
USHORT m_nType;
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) в *справочнике программиста OLE DB* .

## <a name="cenumeratoraccessorm_szdescription"></a><a name="szdescription"></a>CEnumeratorAccessor:: m_szDescription

Описание источника данных или перечислителя.

### <a name="syntax"></a>Синтаксис

```cpp
WCHAR m_szDescription[129];
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) в *справочнике программиста OLE DB* .

## <a name="cenumeratoraccessorm_szname"></a><a name="szname"></a>CEnumeratorAccessor:: m_szName

Имя источника данных или перечислителя.

### <a name="syntax"></a>Синтаксис

```cpp
WCHAR m_szName[129];
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) в *справочнике программиста OLE DB* .

## <a name="cenumeratoraccessorm_szparsename"></a><a name="szparsename"></a>CEnumeratorAccessor:: m_szParseName

Строка для передачи в [ипарседисплайнаме](/windows/win32/api/oleidl/nn-oleidl-iparsedisplayname) для получения моникера для источника данных или перечислителя.

### <a name="syntax"></a>Синтаксис

```cpp
WCHAR m_szParseName[129];
```

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85)) в *справочнике программиста OLE DB* .

## <a name="see-also"></a>См. также:

[Шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)