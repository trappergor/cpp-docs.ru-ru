---
title: "CArrayRowset::operator | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CArrayRowset::operator[]
- CArrayRowset.operator[]
dev_langs: C++
helpviewer_keywords:
- operator [], arrays
- '[] operator'
- operator[], arrays
ms.assetid: 3bb8c310-cc1e-46e8-9711-9b565488acaa
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 61929df340fb12afc5c2abdc6bd9f4e8bd899108
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="carrayrowsetoperator"></a>CArrayRowset::operator
Содержит синтаксис, подобный массиву для доступа строки в наборе строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
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