---
title: CRowset::Close | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset::Close
- ATL.CRowset.Close
- CRowset<TAccessor>::Close
- CRowset<TAccessor>.Close
- ATL.CRowset<TAccessor>.Close
- ATL::CRowset::Close
- ATL::CRowset<TAccessor>::Close
- CRowset.Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 966d779e-e148-4dc0-bbba-7cfb9fa6a16b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b56cd48a61ceab242081c1323a267b21be661ad4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096734"
---
# <a name="crowsetclose"></a>CRowset::Close
Освобождает строки и текущего [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
void Close() throw();  
  
```  
  
## <a name="remarks"></a>Примечания  
 Данный метод освобождает все строки в данный момент в наборе строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowset](../../data/oledb/crowset-class.md)