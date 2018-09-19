---
title: Класс IRowsetCreatorImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
- IRowsetCreatorImpl.SetSite
- IRowsetCreatorImpl<T>::SetSite
- IRowsetCreatorImpl::SetSite
- SetSite
- ATL.IRowsetCreatorImpl.SetSite
- ATL::IRowsetCreatorImpl<T>::SetSite
- ATL::IRowsetCreatorImpl::SetSite
- ATL.IRowsetCreatorImpl<T>.SetSite
dev_langs:
- C++
helpviewer_keywords:
- IRowsetCreatorImpl class
- SetSite method
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 51534ffb027e35bbab5a9473cf4190c14b384808
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118155"
---
# <a name="irowsetcreatorimpl-class"></a>Класс IRowsetCreatorImpl

Выполняет те же функции, что `IObjectWithSite` , но и обеспечивает свойства OLE DB `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS`.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
### <a name="parameters"></a>Параметры  

*T*<br/>
Класс, производный от `IRowsetCreator`.  

## <a name="requirements"></a>Требования  

**Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[SetSite](#setsite)|Задает сайт, который содержит объект набора строк.|  
  
## <a name="remarks"></a>Примечания  

Этот класс наследует от [IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite) и переопределяет [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite). Когда объект команды или сеанса поставщика создает набор строк, он вызывает `QueryInterface` в объекте набора строк, ищете `IObjectWithSite` и вызывает метод `SetSite` передачи объекта набора строк `IUnkown` интерфейс как интерфейс веб-узла.  

## <a name="setsite"></a> IRowsetCreatorImpl::SetSite

Задает сайт, который содержит объект набора строк. Дополнительные сведения см. в разделе [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite).  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);  
```  
  
#### <a name="parameters"></a>Параметры  

*pCreator*<br/>
[in] Указатель на `IUnknown` указатель на интерфейс узла управления в объекте набора строк.  
  
### <a name="return-value"></a>Возвращаемое значение  

Стандартный HRESULT.  
  
### <a name="remarks"></a>Примечания  

Кроме того `IRowsetCreatorImpl::SetSite` позволяет OLE DB `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` свойства. 

## <a name="see-also"></a>См. также  

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)