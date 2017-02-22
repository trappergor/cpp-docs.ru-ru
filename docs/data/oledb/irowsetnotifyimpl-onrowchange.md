---
title: "IRowsetNotifyImpl::OnRowChange | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetNotifyImpl::OnRowChange"
  - "IRowsetNotifyImpl.OnRowChange"
  - "OnRowChange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnRowChange - метод"
ms.assetid: 148bee03-3707-4bbf-8c51-657efc63645f
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# IRowsetNotifyImpl::OnRowChange
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Уведомляет объект\-получатель о первом изменении в строке или о любом изменении, оказывающем влияние на всю строку.  
  
## Синтаксис  
  
```  
  
STDMETHOD(OnRowChange)(   
/* [in] */ IRowset* /* pRowset */,  
/* [in] */ DBCOUNTITEM /* cRows */,  
/* [size_is][in] */ const HROW /* rghRows*/ [] ,  
/* [in] */ DBREASON /* eReason */,  
/* [in] */ DBEVENTPHASE /* ePhase */,  
/* [in] */ BOOL /* fCantDeny */)  
```  
  
#### Параметры  
 См. описание параметра [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx).  
  
## Возвращаемое значение  
 В разделе [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) для описания возвращаемого значения.  
  
## Заметки  
 Этот метод реализует метод [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx).  См. описание этого метода в справочнике программиста OLE DB для сведения.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс IRowsetNotifyImpl](../Topic/IRowsetNotifyImpl%20Class.md)   
 [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx)