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
ms.openlocfilehash: 0c828708a088c8fe31075a8fe8504f3a1f8c14b4
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337101"
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
 *T*  
 Класс, производный от `IRowsetCreator`.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[SetSite](#setsite)|Задает сайт, который содержит объект набора строк.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс наследует от [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) и переопределяет [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869). Когда объект команды или сеанса поставщика создает набор строк, он вызывает `QueryInterface` в объекте набора строк, ищете `IObjectWithSite` и вызывает метод `SetSite` передачи объекта набора строк `IUnkown` интерфейс как интерфейс веб-узла.  

## <a name="setsite"></a> IRowsetCreatorImpl::SetSite
Задает сайт, который содержит объект набора строк. Дополнительные сведения см. в разделе [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869).  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);  
```  
  
#### <a name="parameters"></a>Параметры  
 *pCreator*  
 [in] Указатель на `IUnknown` указатель на интерфейс узла управления в объекте набора строк.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартный HRESULT.  
  
### <a name="remarks"></a>Примечания  
 Кроме того `IRowsetCreatorImpl::SetSite` позволяет OLE DB `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` свойства. 

## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)