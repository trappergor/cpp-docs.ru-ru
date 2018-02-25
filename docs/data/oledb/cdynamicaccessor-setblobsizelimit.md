---
title: "CDynamicAccessor::SetBlobSizeLimit | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicAccessor::SetBlobSizeLimit
- SetBlobSizeLimit
- CDynamicAccessor.SetBlobSizeLimit
- ATL.CDynamicAccessor.SetBlobSizeLimit
- ATL::CDynamicAccessor::SetBlobSizeLimit
dev_langs:
- C++
helpviewer_keywords:
- SetBlobSizeLimit method
ms.assetid: fb8cb85d-f841-408e-a344-37895b10993f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a2fac05c1380e2b612cb39994716387d99bef237
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorsetblobsizelimit"></a>CDynamicAccessor::SetBlobSizeLimit
Задает максимальный размер большого двоичного ОБЪЕКТА в байтах.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      void SetBlobSizeLimit(DBLENGTH nBlobSize);  
```  
  
#### <a name="parameters"></a>Параметры  
 `nBlobSize`  
 Задает предельный размер большого двоичного ОБЪЕКТА.  
  
## <a name="remarks"></a>Примечания  
 Задает максимальный размер большого двоичного ОБЪЕКТА в байтах; данные столбца, размер которых превышает это значение рассматривается как большой двоичный объект. Некоторые поставщики предоставляют слишком большой размер для столбцов (например, 2 ГБ). Вместо того, чтобы выделить память для столбца этот размер, обычно будет выполнена попытка привязать эти столбцы в виде больших двоичных объектов. В этом случае не нужно выделить память, но по-прежнему можно прочитать все данные, не опасаясь усечение. Тем не менее существуют случаи, в которых может потребоваться принудительно `CDynamicAccessor` привязать больших столбцов в их собственных типах данных. Чтобы сделать это, вызовите `SetBlobSizeLimit` перед вызовом **откройте**.  
  
 Метод конструктора [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) задает максимальный размер большого двоичного ОБЪЕКТА значение по умолчанию 8 000 байт.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)