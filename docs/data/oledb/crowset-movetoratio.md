---
title: "CRowset::MoveToRatio | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MoveToRatio"
  - "CRowset<TAccessor>::MoveToRatio"
  - "CRowset::MoveToRatio"
  - "CRowset<TAccessor>.MoveToRatio"
  - "ATL.CRowset.MoveToRatio"
  - "ATL::CRowset::MoveToRatio"
  - "CRowset.MoveToRatio"
  - "ATL.CRowset<TAccessor>.MoveToRatio"
  - "ATL::CRowset<TAccessor>::MoveToRatio"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToRatio - метод"
ms.assetid: 1fa313bd-8fd1-4608-8e85-44993b97dd88
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CRowset::MoveToRatio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Доступ к частичной строки, начиная с позиции в наборе строк.  
  
## Синтаксис  
  
```  
  
      HRESULT MoveToRatio(   
   DBCOUNTITEM nNumerator,   
   DBCOUNTITEM nDenominator,   
   bool bForward = true    
) throw( );  
```  
  
#### Параметры  
 `nNumerator`  
 \[in\] делимое, используемый для определения частичное позиционные из них для получения данных.  
  
 `nDenominator`  
 \[in\] знаменатель, используемый для определения частичное позиционные из них для получения данных.  
  
 `bForward`  
 \[in\] указывает, является ли переместить переднее или его.  По умолчанию переднее.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 `MoveToRatio` выборки строк согласовывая грубо в следующей формуле:  
  
 `( nNumerator *  RowsetSize ) / nDenominator`  
  
 , где `RowsetSize` размер набора строк, измеренный в строках.  Точность этой формулы зависит от конкретного поставщика.  Дополнительные сведения см. в разделе [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx).  
  
 Этот метод требует дополнительного интерфейса `IRowsetScroll`, может не поддерживаться во всех поставщиках; если это так, метод возвращает **E\_NOINTERFACE**.  Необходимо также установить **DBPROP\_IRowsetScroll** в `VARIANT_TRUE` до вызова метода **Открыть** на таблице или команда, содержащий набор строк.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CRowset](../Topic/CRowset%20Class.md)