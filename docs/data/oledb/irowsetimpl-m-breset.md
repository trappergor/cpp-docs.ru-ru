---
title: "IRowsetImpl::m_bReset | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetImpl.m_bReset"
  - "IRowsetImpl.m_bReset"
  - "m_bReset"
  - "IRowsetImpl::m_bReset"
  - "ATL::IRowsetImpl::m_bReset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bReset"
ms.assetid: d423f9f3-4d48-4d0c-b152-684c81a0b34e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::m_bReset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Несколько флажок, используемый для определения, является ли заданная позиция курсора в наборе строк.  
  
## Синтаксис  
  
```  
  
unsigned m_bReset:1;  
  
```  
  
## Заметки  
 Если объект\-получатель вызывает метод [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) с отрицательным `lOffset` или *вороны* и `m_bReset` либо, `GetNextRows` перемещается в конец набора строк.  Если `m_bReset` ложно, объект\-получатель возвращает код ошибки, в соответствуют с спецификации OLE DB.  Флажок `m_bReset` получает набор в набор строк **true** при первоначальном создании и когда объект\-получатель вызывает метод [IRowsetImpl::RestartPosition](../../data/oledb/irowsetimpl-restartposition.md).  Получает набор значение **false** при вызове `GetNextRows`.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IRowsetImpl](../Topic/IRowsetImpl%20Class.md)