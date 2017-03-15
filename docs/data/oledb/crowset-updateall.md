---
title: "CRowset::UpdateAll | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset::UpdateAll"
  - "ATL.CRowset.UpdateAll"
  - "CRowset<TAccessor>.UpdateAll"
  - "ATL.CRowset<TAccessor>.UpdateAll"
  - "UpdateAll"
  - "CRowset.UpdateAll"
  - "ATL::CRowset<TAccessor>::UpdateAll"
  - "CRowset<TAccessor>::UpdateAll"
  - "ATL::CRowset::UpdateAll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UpdateAll - метод"
ms.assetid: e5b26c0a-40fc-4c91-a293-5084951788e6
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::UpdateAll
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Передает все ожидающие изменения всех строк, поскольку последние выборка или вызов **Обновить** на этом компьютере.  
  
## Синтаксис  
  
```  
  
      HRESULT UpdateAll(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW** pphRow = NULL,   
   DBROWSTATUS** ppStatus = NULL    
) throw( );  
```  
  
#### Параметры  
 `pcRows`  
 \[out\] указатель на расположение, `UpdateAll` возвращает число строк, предпринята попытка обновления, если это необходимо.  
  
 `pphRow`  
 \[out\] указатель на памяти, в которой `UpdateAll` возвращает дескриптор строки он попытался обновить.  Отсутствует дескриптор не возвращается, если `pphRow` NULL.  
  
 `ppStatus`  
 \[out\] указатель на расположение, **Обновить** возвращает значение состояния строк.  Нет состояния не возвращается, если `ppStatus` NULL.  
  
## Заметки  
 Передает все изменения, ожидающие изменения всех строк, поскольку эти строки последним были получены удаленный доступ или были обновлены с помощью [Обновить](../Topic/CRowset::Update.md) или `UpdateAll`.  `UpdateAll` обновляет каждую строку, которая была изменена, независимо от того, имеются ли по\-прежнему дескриптор для них \(см. `pphRow`\) или нет.  
  
 Например, при использовании **Вставить** для вставки 5 строк в наборе строк, можно вызвать метод **Обновить** или 5 раз или вызвать `UpdateAll` только для обновления их все.  
  
 Этот метод требует дополнительного интерфейса `IRowsetUpdate`, может не поддерживаться во всех поставщиках; если это так, метод возвращает **E\_NOINTERFACE**.  Необходимо также установить **DBPROP\_IRowsetUpdate** в `VARIANT_TRUE` до вызова метода **Открыть** на таблице или команда, содержащий набор строк.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CRowset](../Topic/CRowset%20Class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)   
 [CRowset::Update](../Topic/CRowset::Update.md)