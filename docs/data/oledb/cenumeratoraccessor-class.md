---
title: Класс CEnumeratorAccessor | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CEnumeratorAccessor class
- m_bIsParent
- m_nType
- m_szDescription
- m_szName
- m_szParseName
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 896c1dd1f1d3a43a3678a086d80e0f95b60b6126
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083337"
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

См. в разделе [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200) в *Справочник программиста OLE DB по* Дополнительные сведения. 

## <a name="ntype"></a> CEnumeratorAccessor::m_nType

Переменная, указывающее, является ли строка описывает источник данных или перечислителя.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
USHORT m_nType;  
```  
  
### <a name="remarks"></a>Примечания  

См. в разделе [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200) в *Справочник программиста OLE DB по* Дополнительные сведения.

## <a name="szdescription"></a> CEnumeratorAccessor::m_szDescription

Описание источника данных или перечислителя.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
WCHAR m_szDescription[129];  
```  
  
### <a name="remarks"></a>Примечания  

См. в разделе [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200) в *Справочник программиста OLE DB по* Дополнительные сведения.

## <a name="szname"></a> CEnumeratorAccessor::m_szName

Имя источника данных или перечислителя.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
WCHAR m_szName[129];  
```  
  
### <a name="remarks"></a>Примечания  

См. в разделе [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200) в *Справочник программиста OLE DB по* Дополнительные сведения.  

## <a name="szparsename"></a> CEnumeratorAccessor::m_szParseName

Строка, передаваемая для [IParseDisplayName](/windows/desktop/api/oleidl/nn-oleidl-iparsedisplayname) для получения моникера для источника данных или перечислителя.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
WCHAR m_szParseName[129];  
```  
  
### <a name="remarks"></a>Примечания  

См. в разделе [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200) в *Справочник программиста OLE DB по* Дополнительные сведения.  
  
## <a name="see-also"></a>См. также  

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)