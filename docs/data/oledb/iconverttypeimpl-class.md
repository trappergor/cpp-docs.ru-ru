---
title: Класс IConvertTypeImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b9a8fdef3abf0c33fb6fca857086e6490ec959e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100048"
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