---
title: "CRowset::SetData | Microsoft Docs"
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
  - "ATL.CRowset<TAccessor>.SetData"
  - "SetData"
  - "ATL::CRowset::SetData"
  - "CRowset<TAccessor>.SetData"
  - "CRowset::SetData"
  - "ATL.CRowset.SetData"
  - "CRowset.SetData"
  - "CRowset<TAccessor>::SetData"
  - "ATL::CRowset<TAccessor>::SetData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetData - метод"
ms.assetid: 68125142-8510-4132-9393-e39efd39c784
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::SetData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает значения данных в одном или нескольких столбцах строки.  
  
## Синтаксис  
  
```  
  
      HRESULT SetData( ) const throw( );   
HRESULT SetData(  
   int nAccessor   
) const throw( );  
```  
  
#### Параметры  
 `nAccessor`  
 \[in\] число доступа используется для доступа к данным.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Для формы `SetData`, не принимает аргументов, все методы доступа используются для обновления.  Обычно вызывается метод **SetData**  для задания значений данных в столбцах в строке, а затем вызвать [Обновить](../Topic/CRowset::Update.md), чтобы передать эти изменения.  
  
 Этот метод требует дополнительного интерфейса `IRowsetChange`, может не поддерживаться во всех поставщиках; если это так, метод возвращает **E\_NOINTERFACE**.  Необходимо также установить **DBPROP\_IRowsetChange** в `VARIANT_TRUE` до вызова метода **Открыть** на таблице или команда, содержащий набор строк.  
  
 Операция параметра может завершиться неудачей, если один или несколько столбцов недоступны для записи.  Чтобы устранить эти ошибки, измените таблицу курсоров.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CRowset](../Topic/CRowset%20Class.md)   
 [CRowset::Update](../Topic/CRowset::Update.md)