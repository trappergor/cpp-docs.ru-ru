---
title: Перечисление AsyncResultType | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
dev_langs:
- C++
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: de4a8465dd61e52425a0335e171cf516591ae589
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType - перечисление
Указывает тип результата, возвращаемого методом GetResults().  
  
## <a name="syntax"></a>Синтаксис  
  
```  
enum AsyncResultType;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="values"></a>Значения  
  
|Имя|Описание|  
|----------|-----------------|  
|`MultipleResults`|Набор несколько результатов, представленных постепенно между начальное состояние, и перед вызовом Close().|  
|`SingleResult`|Один результат, который представлен после завершения события.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)