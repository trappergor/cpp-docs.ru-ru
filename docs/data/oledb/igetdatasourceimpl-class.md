---
title: "Класс IGetDataSourceImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IGetDataSourceImpl
- ATL.IGetDataSourceImpl<T>
- ATL.IGetDataSourceImpl
- ATL::IGetDataSourceImpl
- ATL::IGetDataSourceImpl<T>
dev_langs: C++
helpviewer_keywords: IGetDataSourceImpl class
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c83ab71b7b19d410dd0157f3400ebc1a58a63916
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="igetdatasourceimpl-class"></a>Класс IGetDataSourceImpl
Предоставляет реализацию [IGetDataSource](https://msdn.microsoft.com/en-us/library/ms709721.aspx) объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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