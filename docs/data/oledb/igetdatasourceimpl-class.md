---
title: Класс IGetDataSourceImpl | Документы Microsoft
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
dev_langs:
- C++
helpviewer_keywords:
- IGetDataSourceImpl class
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 50ffa3f176bbd5691a3ea0bc4e23aa8245712e17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101114"
---
# <a name="igetdatasourceimpl-class"></a>Класс IGetDataSourceImpl
Предоставляет реализацию [IGetDataSource](https://msdn.microsoft.com/en-us/library/ms709721.aspx) объекта.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T>  
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IGetDataSourceImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[GetDataSource](../../data/oledb/igetdatasourceimpl-getdatasource.md)|Возвращает указатель интерфейса на объект источника данных, для которого был создан сеанс.|  
  
## <a name="remarks"></a>Примечания  
 Это обязательный интерфейс для получения указателя на интерфейс для объекта источника данных в сеансе.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)