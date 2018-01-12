---
title: "Класс CUtlProps | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CUtlProps
dev_langs: C++
helpviewer_keywords: CUtlProps class
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 75e92f48729d0aae9f85cc7b7c5c97e4778f96a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cutlprops-class"></a>Класс CUtlProps
Реализует свойства для различных свойств интерфейсы OLE DB (например, `IDBProperties`, `IDBProperties`, и `IRowsetInfo`).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template < class T >  
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, содержащий `BEGIN_PROPSET_MAP`.  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[GetPropValue](../../data/oledb/cutlprops-getpropvalue.md)|Возвращает свойство из набора свойств.|  
|[IsValidValue](../../data/oledb/cutlprops-isvalidvalue.md)|Используется для проверки значения перед заданием свойства.|  
|[OnInterfaceRequested](../../data/oledb/cutlprops-oninterfacerequested.md)|Обрабатывает запросы к дополнительный интерфейс, когда потребитель вызывает метод в интерфейсе создания объекта.|  
|[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)|Вызывается после задания свойства для обработки связанных свойств.|  
|[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)|Задает свойство в наборе свойств.|  
  
## <a name="remarks"></a>Примечания  
 Большая часть этого класса является элементом реализации.  
  
 `CUtlProps`содержит два элемента для настройки свойств внутренне: [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) и [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).  
  
 Дополнительные сведения о макросы, используемые в сопоставление набора свойств см. в разделе [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md) и [END_PROPSET_MAP](../../data/oledb/end-propset-map.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)