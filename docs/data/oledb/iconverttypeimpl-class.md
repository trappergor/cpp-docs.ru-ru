---
title: "Класс IConvertTypeImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IConvertTypeImpl<T>
- IConvertTypeImpl
- ATL.IConvertTypeImpl
- ATL::IConvertTypeImpl
- ATL::IConvertTypeImpl<T>
dev_langs: C++
helpviewer_keywords: IConvertTypeImpl class
ms.assetid: 7f81e79e-7d3f-4cbe-b93c-d632a94b15f6
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 293d5d02b9515db7356eb839ced8dc1d006daafb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="iconverttypeimpl-class"></a>Класс IConvertTypeImpl
Предоставляет реализацию [IConvertType](https://msdn.microsoft.com/en-us/library/ms715926.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class T>  
class ATL_NO_VTABLE IConvertTypeImpl   
   : public IConvertType, public CConvertHelper  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IConvertTypeImpl`.  
  
## <a name="members"></a>Члены  
  
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