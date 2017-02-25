---
title: "CRowsetImpl::ValidateCommandID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowsetImpl.ValidateCommandID"
  - "CRowsetImpl::ValidateCommandID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ValidateCommandID - метод"
ms.assetid: cdde6088-41bc-4b8f-a32b-f36f7d9b5ec0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowsetImpl::ValidateCommandID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли любой или и **DBID**, содержащий строковые значения, и если да, скопируйте их в элементов данных [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## Синтаксис  
  
```  
  
      HRESULT CRowsetBaseImpl::ValidateCommandID(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### Параметры  
 `pTableID`  
 \[in\] указатель на **DBID**, представляющая идентификатор таблицы  
  
 `pIndexID`  
 \[in\] указатель на **DBID**, представляющий индекс идентификатор.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Этот метод вызывается с помощью статического upcast `CRowsetImpl` для заполнения его элементы данных [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  По умолчанию этот метод проверяет, попадает ли одно или оба **DBID**, содержащий строковые значения, и если да, скопируйте их в элементов данных.  Устанавливая метод с данной сигнатурой в `CRowsetImpl`\- производный класс, этот метод вызывается вместо базовой реализации.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс CRowsetImpl](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)