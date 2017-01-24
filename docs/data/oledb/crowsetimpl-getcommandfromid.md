---
title: "CRowsetImpl::GetCommandFromID | Microsoft Docs"
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
  - "CRowsetImpl::GetCommandFromID"
  - "GetCommandFromID"
  - "CRowsetImpl.GetCommandFromID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCommandFromID - метод"
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::GetCommandFromID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проверяет, является ли один или оба параметры содержат строковые значения, и если да, копирования строковые значения элементам данных [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## Синтаксис  
  
```  
  
      HRESULT CRowsetBaseImpl::GetCommandFromID(  
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
 Этот метод вызывается с помощью статического upcast `CRowsetImpl` для заполнения элементов данных [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  По умолчанию этот метод проверяет, попадает ли один или оба параметры содержат строковые значения.  Если они содержат строковые значения, копии этого метода строковые значения элементам данных.  Устанавливая метод с данной сигнатурой в `CRowsetImpl`\- производный класс, этот метод вызывается вместо базовой реализации.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс CRowsetImpl](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)