---
title: "CRowset::FindNextRow | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CRowset.FindNextRow"
  - "CRowset<TAccessor>.FindNextRow"
  - "ATL::CRowset::FindNextRow"
  - "CRowset::FindNextRow"
  - "CRowset<TAccessor>::FindNextRow"
  - "CRowset.FindNextRow"
  - "ATL.CRowset<TAccessor>.FindNextRow"
  - "ATL::CRowset<TAccessor>::FindNextRow"
  - "FindNextRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FindNextRow - метод"
ms.assetid: 36484df9-3625-4f15-bf69-db73a8d91c55
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::FindNextRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Находит следующую строку сопоставления после определенной закладки.  
  
## Синтаксис  
  
```  
  
      HRESULT FindNextRow(   
   DBCOMPAREOP op,   
   BYTE* pData,   
   DBTYPE wType,   
   DBLENGTH nLength,   
   BYTE bPrecision,   
   BYTE bScale,   
   BOOL bSkipCurrent = TRUE,   
   CBookmarkBase* pBookmark = NULL    
) throw( );  
```  
  
#### Параметры  
 `op`  
 \[in\] операции, используемый при сравнении значения строки.  Для значений см. в разделе [IRowsetFind::FindNextRow](https://msdn.microsoft.com/en-us/library/ms723091.aspx).  
  
 `pData`  
 \[in\] указатель на значение для сравнения.  
  
 `wType`  
 \[in\] указывает тип данных значения части буфера.  Дополнительные сведения об индикаторах типа см. в разделе [Типы данных](https://msdn.microsoft.com/en-us/library/ms723969.aspx) справочника *программиста по OLE DB* в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nLength`  
 \[in\] размер, в байтах, структуры данных объект\-получателя выбранной для данных значение.  Дополнительные сведения см. в описании **cbMaxLen** см. в разделе [Структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) в *справочнике программиста OLE DB.*  
  
 `bPrecision`  
 \[in\] максимальная точность, используемая при получении данных.  Используется только в том случае, если `wType``DBTYPE_NUMERIC`.  Дополнительные сведения см. в разделе [Преобразования, включающие DBTYPE\_DECIMAL или DBTYPE\_NUMERIC](https://msdn.microsoft.com/en-us/library/ms719714.aspx) в *справочнике программиста OLE DB*.  
  
 `bScale`  
 \[in\] масштаб, используемый при получении данных.  Используется только в том случае, если `wType``DBTYPE_NUMERIC` или **DBTYPE\_DECIMAL**.  Дополнительные сведения см. в разделе [Преобразования, включающие DBTYPE\_DECIMAL или DBTYPE\_NUMERIC](https://msdn.microsoft.com/en-us/library/ms719714.aspx) в *справочнике программиста OLE DB*.  
  
 *bSkipCurrent*  
 \[in\] количество строк из закладки в, чтобы начать поиск.  
  
 `pBookmark`  
 \[in\] закладки в той же позиции в которой начинается поиск.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Этот метод требует дополнительного интерфейса **IRowsetFind**, который может не поддерживаться во всех поставщиках; если это так, метод возвращает **E\_NOINTERFACE**.  Необходимо также установить **DBPROP\_IRowsetFind** в `VARIANT_TRUE` до вызова метода **Открыть** на таблице или команда, содержащий набор строк.  
  
 Дополнительные сведения об использовании закладок в объект\-получателях см. в разделе [С помощью закладок](../../data/oledb/using-bookmarks.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CRowset](../Topic/CRowset%20Class.md)   
 [DBBINDING Structures](https://msdn.microsoft.com/en-us/library/ms716845.aspx)