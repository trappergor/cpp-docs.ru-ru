---
title: "IOpenRowsetImpl::CreateRowset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IOpenRowsetImpl.CreateRowset"
  - "IOpenRowsetImpl::CreateRowset"
  - "CreateRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateRowset - метод"
ms.assetid: 69041cf6-7a2f-4409-a26e-6e984c24986e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IOpenRowsetImpl::CreateRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает объект набора строк.  Не вызывается непосредственно пользователем.  В разделе [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) справочника *программиста OLE DB.*  
  
## Синтаксис  
  
```  
  
      template <class   
      RowsetClass  
      >  
HRESULT CreateRowset(  
   IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj   
);  
```  
  
#### Параметры  
 `RowsetClass`  
 Член класса шаблона, представляющий класс набора строк пользователя.  Как правило, созданный мастером.  
  
 `pRowsetObj`  
 \[out\] указатель на объект набора строк.  Обычно этот параметр не используется, но можно использовать, если необходимо выполнить несколько операций в наборе строк, перед передачей их com\-объекта.  Время существования `pRowsetObj` привязано `ppRowset`.  
  
 Для других параметров см. в разделе [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) справочника *программиста OLE DB.*  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)