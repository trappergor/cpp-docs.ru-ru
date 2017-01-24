---
title: "CBulkRowset::MoveToRatio | Microsoft Docs"
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
  - "CBulkRowset.MoveToRatio"
  - "ATL::CBulkRowset::MoveToRatio"
  - "MoveToRatio"
  - "CBulkRowset::MoveToRatio"
  - "ATL.CBulkRowset<TAccessor>.MoveToRatio"
  - "ATL::CBulkRowset<TAccessor>::MoveToRatio"
  - "ATL.CBulkRowset.MoveToRatio"
  - "CBulkRowset<TAccessor>::MoveToRatio"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToRatio - метод"
ms.assetid: 86be60f5-9341-44c1-8e1e-9174c082d0d5
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBulkRowset::MoveToRatio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Доступ к частичной строки, начиная с позиции в наборе строк.  
  
## Синтаксис  
  
```  
  
      HRESULT MoveToRatio(  
   DBCOUNTITEM nNumerator,  
   DBCOUNTITEM nDenominator   
) throw( );  
```  
  
#### Параметры  
 `nNumerator`  
 \[in\] делимое, используемый для определения частичную положение, из которой доступ к данным.  
  
 `nDenominator`  
 \[in\] знаменатель, используемый для определения частичную положение, из которой доступ к данным.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 `MoveToRatio` выборки строк грубо по следующей формуле:  
  
 `( nNumerator *  RowsetSize ) / nDenominator`  
  
 , Где `RowsetSize` размер набора строк, измеренный в строках.  Точность этой формулы зависит от конкретного поставщика.  Дополнительные сведения см. в разделе [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx) справочника *программиста OLE DB*.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CBulkRowset](../Topic/CBulkRowset%20Class.md)