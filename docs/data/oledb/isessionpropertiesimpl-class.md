---
title: "Класс ISessionPropertiesImpl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ISessionPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISessionPropertiesImpl - класс"
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Класс ISessionPropertiesImpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет реализацию интерфейса [ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx).  
  
## Синтаксис  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
#### Параметры  
 `T`  
 Класс, производный от `ISessionPropertiesImpl`.  
  
 `PropClass`  
 Класс определимый пользователем свойства, устанавливается значение по умолчанию `T`.  
  
## Члены  
  
### Методы Interface  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)|Возвращает список свойств в группе свойств сеанса, в настоящее время установлены на сеанс.|  
|[SetProperties](../../data/oledb/isessionpropertiesimpl-setproperties.md)|Задает свойства в группе свойств сеанса.|  
  
## Заметки  
 Обязательный интерфейс на сеансах.  Этот класс реализует свойства сеанса, вызвав статическая функция, [сопоставление набора свойств](../Topic/BEGIN_PROPSET_MAP.md).  Сопоставление набора свойств должно быть указано в классе сеанса.  
  
## Требования  
 **Header:**  atldb.h  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)