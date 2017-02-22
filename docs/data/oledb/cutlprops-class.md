---
title: "Класс CUtlProps | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CUtlProps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUtlProps - класс"
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Класс CUtlProps
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует свойства для различных интерфейсов свойства OLE DB \(например, `IDBProperties`, `IDBProperties` и `IRowsetInfo`\).  
  
## Синтаксис  
  
```  
template < class T >  
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase  
```  
  
#### Параметры  
 `T`  
 Класс, содержащий `BEGIN_PROPSET_MAP`.  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[GetPropValue](../Topic/CUtlProps::GetPropValue.md)|Получает свойство из набора свойств.|  
|[IsValidValue](../../data/oledb/cutlprops-isvalidvalue.md)|Используется для проверки, прежде чем устанавливать свойство.|  
|[OnInterfaceRequested](../../data/oledb/cutlprops-oninterfacerequested.md)|Обрабатывает запросы для дополнительного интерфейса, когда объект\-получатель вызывает метод в интерфейсе поколения объектов.|  
|[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)|Вызывается после установки свойства дескриптора приковал свойства.|  
|[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)|Задает свойство в набор свойств.|  
  
## Заметки  
 Большая часть этого класса подробности реализации.  
  
 `CUtlProps` содержит 2 члена для настройки свойств внутренне: [GetPropValue](../Topic/CUtlProps::GetPropValue.md) и [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).  
  
 Дополнительные сведения о макросах, используемых в сопоставлении набора свойств см. в разделах [BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md) и [END\_PROPSET\_MAP](../../data/oledb/end-propset-map.md).  
  
## Требования  
 **Header:**  atldb.h  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)