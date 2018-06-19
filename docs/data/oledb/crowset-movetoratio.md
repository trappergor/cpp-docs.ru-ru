---
title: CRowset::MoveToRatio | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- MoveToRatio method
ms.assetid: 1fa313bd-8fd1-4608-8e85-44993b97dd88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9c864933070af4f2a40572d0133027fb81f0855a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096669"
---
# <a name="crowsetmovetoratio"></a>CRowset::MoveToRatio
Извлекает строки, начиная с долей позиции в наборе строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,   
   DBCOUNTITEM nDenominator,bool bForward = true) throw();  
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
 `MoveToRatio` Извлекает строки, в соответствии с примерно следующую формулу:  
  
 `(nNumerator *  RowsetSize ) / nDenominator`  
  
 Где `RowsetSize` равно размеру набора строк, измеряемый в строках. Точность по этой формуле, зависит от конкретного поставщика. Дополнительные сведения см. в разделе [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx).  
  
 Этот метод требует дополнительный интерфейс `IRowsetScroll`, который может поддерживается не всеми поставщиками; Если это так, метод возвращает **E_NOINTERFACE**. Необходимо также задать **DBPROP_IRowsetScroll** для `VARIANT_TRUE` перед вызовом **откройте** для таблицы или команду, содержащую набор строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowset](../../data/oledb/crowset-class.md)