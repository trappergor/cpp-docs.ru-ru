---
title: Класс IDBCreateCommandImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IDBCreateCommandImpl
- IDBCreateCommandImpl
- ATL.IDBCreateCommandImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateCommandImpl class
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cc032a488626f2d366152f2d2b70b2539b9137b9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101530"
---
# <a name="idbcreatecommandimpl-class"></a>Класс IDBCreateCommandImpl
Предоставляет реализацию [IDBCreateCommand](https://msdn.microsoft.com/en-us/library/ms711625.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class CommandClass >  
class ATL_NO_VTABLE IDBCreateCommandImpl   
   : public IDBCreateCommand  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Объект сеанса, производный от `IDBCreateCommandImpl`.  
  
 `CommandClass`  
 Класс команд.  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[CreateCommand](../../data/oledb/idbcreatecommandimpl-createcommand.md)|Создание новой команды.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительный интерфейс для объекта сеанса, чтобы получить к ней новой команды.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)