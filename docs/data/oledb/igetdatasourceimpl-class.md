---
title: Класс IGetDataSourceImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IGetDataSourceImpl
- ATL.IGetDataSourceImpl<T>
- ATL.IGetDataSourceImpl
- ATL::IGetDataSourceImpl
- ATL::IGetDataSourceImpl<T>
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
dev_langs:
- C++
helpviewer_keywords:
- IGetDataSourceImpl class
- GetDataSource method
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0c6e304547af06d5de6d81bae2ceace119e4681d
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339800"
---
# <a name="igetdatasourceimpl-class"></a>Класс IGetDataSourceImpl
Предоставляет реализацию [IGetDataSource](https://msdn.microsoft.com/library/ms709721.aspx) объекта.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T>  
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IGetDataSourceImpl`.  

## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[GetDataSource](#getdatasource)|Возвращает указатель интерфейса на объект источника данных, создавшего сеанс.|  
  
## <a name="remarks"></a>Примечания  
 Это обязательный интерфейс во время сеанса получение указатель интерфейса на объект источника данных.  

## <a name="getdatasource"></a> IGetDataSourceImpl::GetDataSource
Возвращает указатель интерфейса на объект источника данных, создавшего сеанс.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp
STDMETHOD(GetDataSource)(REFIID riid,   
   IUnknown ** ppDataSource);  
```  
  
#### <a name="parameters"></a>Параметры  
 См. в разделе [IGetDataSource::GetDataSource](https://msdn.microsoft.com/library/ms725443.aspx) в *справочнике программиста OLE DB*.  
  
### <a name="remarks"></a>Примечания  
 Полезно, если вам нужно получить доступ к свойствам в объекте источника данных.  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)