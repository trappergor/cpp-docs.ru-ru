---
title: Класс IRowsetIdentityImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
- IsSameRow
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
dev_langs:
- C++
helpviewer_keywords:
- IRowsetIdentityImpl class
- IsSameRow method
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 55c9b4b7e14a9572f5a8922b65a41a9a92a0d688
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337713"
---
# <a name="irowsetidentityimpl-class"></a>Класс IRowsetIdentityImpl
Реализует OLE DB [IRowsetIdentity](https://msdn.microsoft.com/library/ms715913.aspx) интерфейс, позволяющий тестирования для идентификации строки.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class RowClass = CSimpleRow>  
class ATL_NO_VTABLE IRowsetIdentityImpl   
   : public IRowsetIdentity  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Класс, производный от `IRowsetIdentityImpl`.  
  
 *RowClass*  
 Единица хранения для `HROW`.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[IsSameRow](#issamerow)|Сравнение дескрипторов двух строк, чтобы увидеть, если они ссылаются на той же строке.|  
  
## <a name="issamerow"></a> IRowsetIdentityImpl::IsSameRow
Сравнение дескрипторов двух строк, чтобы увидеть, если они ссылаются на той же строке.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(IsSameRow )(HROW hThisRow,  
   HROW hThatRow);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/library/ms719629.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="remarks"></a>Примечания  
 Чтобы сравнить дескрипторов строк, этот метод приводит `HROW` дескрипторы для `RowClass` члены и вызовы `memcmp` над указателями.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)