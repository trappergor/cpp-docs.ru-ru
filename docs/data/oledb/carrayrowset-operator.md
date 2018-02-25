---
title: "CArrayRowset::operator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CArrayRowset::operator[]
- CArrayRowset.operator[]
dev_langs:
- C++
helpviewer_keywords:
- operator [], arrays
- '[] operator'
- operator[], arrays
ms.assetid: 3bb8c310-cc1e-46e8-9711-9b565488acaa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b2dd001dc3946a3eb22b793874ba1f4b16affb72
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="carrayrowsetoperator"></a>CArrayRowset::operator
Содержит синтаксис, подобный массиву для доступа строки в наборе строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      TAccessor  
      & operator[](int nrow);  
```  
  
#### <a name="parameters"></a>Параметры  
 `TAccessor`  
 Шаблонные параметр, который указывает тип метода доступа, хранящиеся в наборе строк.  
  
 `nRow`  
 [in] Номер строки (элемент массива), необходимо получить доступ к.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Содержимое Запрошенная строка.  
  
## <a name="remarks"></a>Примечания  
 Если `nRow` превышает количество строк в наборе строк, возникает исключение.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CArrayRowset](../../data/oledb/carrayrowset-class.md)