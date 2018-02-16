---
title: "Класс IConvertTypeImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
dev_langs:
- C++
helpviewer_keywords:
- IConvertTypeImpl class
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e19d10b061cd5126f46f2f54a4489caf6d26d40b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="iconverttypeimpl-class"></a>Класс IConvertTypeImpl
Предоставляет реализацию [IConvertType](https://msdn.microsoft.com/en-us/library/ms715926.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T>  
class ATL_NO_VTABLE IConvertTypeImpl   
   : public IConvertType, public CConvertHelper  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IConvertTypeImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[CanConvert](../../data/oledb/iconverttypeimpl-canconvert.md)|Сведения о доступности преобразований типа команды или для набора строк.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс является обязательным на наборы строк, команды и наборы строк индекса. **IConvertTypeImpl** реализует интерфейс путем делегирования для преобразования объекта, заданного параметром OLE DB.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)