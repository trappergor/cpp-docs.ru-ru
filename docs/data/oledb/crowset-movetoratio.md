---
title: "CRowset::MoveToRatio | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MoveToRatio
- CRowset<TAccessor>::MoveToRatio
- CRowset::MoveToRatio
- CRowset<TAccessor>.MoveToRatio
- ATL.CRowset.MoveToRatio
- ATL::CRowset::MoveToRatio
- CRowset.MoveToRatio
- ATL.CRowset<TAccessor>.MoveToRatio
- ATL::CRowset<TAccessor>::MoveToRatio
dev_langs: C++
helpviewer_keywords: MoveToRatio method
ms.assetid: 1fa313bd-8fd1-4608-8e85-44993b97dd88
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 70b4d7994bb2175d0d402fdd309a8258f7127dc7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="crowsetmovetoratio"></a>CRowset::MoveToRatio
Извлекает строки, начиная с долей позиции в наборе строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT MoveToRatio(   
   DBCOUNTITEM nNumerator,   
   DBCOUNTITEM nDenominator,   
   bool bForward = true    
) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 `nNumerator`  
 [in] Числитель, используемый для определения доли позиционные, из которого требуется извлечь данные.  
  
 `nDenominator`  
 [in] Знаменатель, используемый для определения доли позиционные, из которого требуется извлечь данные.  
  
 `bForward`  
 [in] Указывает, требуется ли переместить вперед или назад. Значение по умолчанию — вперед.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 `MoveToRatio`Извлекает строки, в соответствии с примерно следующую формулу:  
  
 `( nNumerator *  RowsetSize ) / nDenominator`  
  
 Где `RowsetSize` равно размеру набора строк, измеряемый в строках. Точность по этой формуле, зависит от конкретного поставщика. Дополнительные сведения см. в разделе [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx).  
  
 Этот метод требует дополнительный интерфейс `IRowsetScroll`, который может поддерживается не всеми поставщиками; Если это так, метод возвращает **E_NOINTERFACE**. Необходимо также задать **DBPROP_IRowsetScroll** для `VARIANT_TRUE` перед вызовом **откройте** для таблицы или команду, содержащую набор строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowset](../../data/oledb/crowset-class.md)