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
ms.openlocfilehash: 9ecc830937e36e213177205549ee4dd4e989e0ed
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118704"
---
# <a name="igetdatasourceimpl-class"></a>Класс IGetDataSourceImpl

Предоставляет реализацию [IGetDataSource](/previous-versions/windows/desktop/ms709721\(v=vs.85\)) объекта.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T>  
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource  
```  
  
### <a name="parameters"></a>Параметры  

*T*<br/>
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

См. в разделе [IGetDataSource::GetDataSource](/previous-versions/windows/desktop/ms725443\(v=vs.85\)) в *справочнике программиста OLE DB*.  
  
### <a name="remarks"></a>Примечания  

Полезно, если вам нужно получить доступ к свойствам в объекте источника данных.  
  
## <a name="see-also"></a>См. также  

[Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)