---
title: "CRowset::MoveToBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CRowset::MoveToBookmark"
  - "ATL::CRowset<TAccessor>::MoveToBookmark"
  - "ATL.CRowset.MoveToBookmark"
  - "ATL.CRowset<TAccessor>.MoveToBookmark"
  - "MoveToBookmark"
  - "CRowset::MoveToBookmark"
  - "CRowset.MoveToBookmark"
  - "CRowset<TAccessor>::MoveToBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToBookmark - метод"
ms.assetid: 90124723-8daf-4692-ae2f-0db26b5db920
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::MoveToBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Доступа к строке, помеченной закладкой или строка с указанным смещением \(`lSkip`\) из этой закладки.  
  
## Синтаксис  
  
```  
  
      HRESULT MoveToBookmark(   
   const CBookmarkBase& bookmark,   
   LONG lSkip = 0    
) throw( );  
```  
  
#### Параметры  
 `bookmark`  
 \[in\] закладки a пометки расположение, из которого необходимо получить данные.  
  
 `lSkip`  
 \[in\] количество номера строк из закладок в строке целевого объекта.  Если `lSkip` ноль, то первая строка удаленный доступ полученная строка создать закладку.  Если `lSkip` 1, то первая строка удаленный доступ полученная строка после создать закладку строки.  Если `lSkip` — 1, полученная удаленный доступ первая строка является строкой перед строкой создать закладку.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Этот метод требует дополнительного интерфейса `IRowsetLocate`, может не поддерживаться во всех поставщиках; если это так, метод возвращает **E\_NOINTERFACE**.  Необходимо также установить **DBPROP\_IRowsetLocate** в `VARIANT_TRUE` и установленному **DBPROP\_CANFETCHBACKWARDS** в `VARIANT_TRUE` до вызова метода **Открыть** на таблице или команда, содержащий набор строк.  
  
 Дополнительные сведения об использовании закладок в объект\-получателях см. в разделе [С помощью закладок](../../data/oledb/using-bookmarks.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CRowset](../Topic/CRowset%20Class.md)   
 [CRowset::MoveNext](../../data/oledb/crowset-movenext.md)   
 [CRowset::MoveFirst](../../data/oledb/crowset-movefirst.md)   
 [IRowsetLocate::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx)   
 [CRowset::MovePrev](../../data/oledb/crowset-moveprev.md)   
 [CRowset::MoveLast](../../data/oledb/crowset-movelast.md)