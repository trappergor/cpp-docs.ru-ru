---
title: Класс ISessionPropertiesImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ISessionPropertiesImpl
dev_langs:
- C++
helpviewer_keywords:
- ISessionPropertiesImpl class
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 62b1321c9d7d50ff2cd459b395efa1e8147a06ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106054"
---
# <a name="isessionpropertiesimpl-class"></a>Класс ISessionPropertiesImpl
Предоставляет реализацию [ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `ISessionPropertiesImpl`.  
  
 `PropClass`  
 Класс определяемые пользователем свойства, значение по умолчанию `T`.  
  
## <a name="members"></a>Участники  
  
### <a name="interface-methods"></a>Методы интерфейса  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)|Возвращает список свойств в группе свойств сеанса, заданных в настоящее время в сеансе.|  
|[SetProperties](../../data/oledb/isessionpropertiesimpl-setproperties.md)|Задает свойства в группе свойств сеанса.|  
  
## <a name="remarks"></a>Примечания  
 Обязательный интерфейс для сеансов. Этот класс реализует свойства сеанса, вызвав статическую функцию, определяемую [сопоставление набора свойств](../../data/oledb/begin-propset-map.md). Сопоставление набора свойств должен быть указан в классе сеанса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)