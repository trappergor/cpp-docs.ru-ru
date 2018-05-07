---
title: CArrayRowset::operator | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 755e484f430f47eb072e3c590bfbee8471984bb6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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