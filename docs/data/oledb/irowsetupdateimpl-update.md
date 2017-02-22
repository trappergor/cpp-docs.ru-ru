---
title: "IRowsetUpdateImpl::Update | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IRowsetUpdateImpl::Update"
  - "IRowsetUpdateImpl::Update"
  - "IRowsetUpdateImpl.Update"
  - "ATL.IRowsetUpdateImpl.Update"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Update - метод"
ms.assetid: 9ec6884d-aa9c-4871-a803-c048f162403c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetUpdateImpl::Update
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Передает все изменения, внесенные в строке с момента последней выборки или обновление.  
  
## Синтаксис  
  
```  
  
      STDMETHOD ( Update )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus   
);  
```  
  
#### Параметры  
 `hReserved`  
 \[in\] соответствует параметру `hChapter` в [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx).  
  
 Для других параметров см. в разделе [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx) справочника *программиста OLE DB*.  
  
## Заметки  
 Изменения передаются с помощью метода [IRowsetChangeImpl::FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md).  Объект\-получатель должен вызвать метод [CRowset::Update](../Topic/CRowset::Update.md) для изменения вступили в силу.  Задайте соответствующее значение *prgRowstatus*, как описано в разделе [Строки состояния](https://msdn.microsoft.com/en-us/library/ms722752.aspx) в *справочнике программиста OLE DB*.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IRowsetUpdateImpl](../Topic/IRowsetUpdateImpl%20Class.md)