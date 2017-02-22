---
title: "CRowsetImpl::NameFromDBID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowsetImpl.NameFromDBID"
  - "CRowsetImpl::NameFromDBID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NameFromDBID - метод"
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowsetImpl::NameFromDBID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлекает строки из **DBID** и копирует ее в `bstr` проведенному недопустимо.  
  
## Синтаксис  
  
```  
  
      HRESULT CRowsetBaseImpl::NameFromDBID(  
   DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex   
);  
```  
  
#### Параметры  
 *pDBID*  
 \[in\] указатель на **DBID**, из которого для извлечения строки.  
  
 `bstr`  
 \[in\] ссылка [CComBSTR](../../atl/reference/ccombstr-class.md) для задания скопировать строки **DBID**.  
  
 `bIndex`  
 \[in\] **true**, если индекс **DBID**; **false**, если в таблице **DBID**.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  В зависимости от того **DBID** таблица или индекс \(имеющего `bIndex`\), или метод возвращает **DB\_E\_NOINDEX** или **DB\_E\_NOTABLE**.  
  
## Заметки  
 Этот метод вызывается реализациями `CRowsetImpl`[ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) и [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md).  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс CRowsetImpl](../../data/oledb/crowsetimpl-class.md)