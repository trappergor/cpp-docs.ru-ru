---
title: "_pAtlModule | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ATLBASE/ATL::_pAtlModule
dev_langs: C++
helpviewer_keywords:
- pAtlModule variable
- _pAtlModule variable
ms.assetid: 0ecde3a9-3f4d-4c7b-bb54-713ce05c4777
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fda7463fbf4ad9d60092572266a78c2c67b9ad59
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="patlmodule"></a>_pAtlModule
Глобальная переменная сохранения указателя к текущему модулю.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__declspec(selectany) CAtlModule* _pAtlModule  
```  
  
## <a name="remarks"></a>Примечания  
 Методы в этой глобальной переменной может использоваться для обеспечения функциональности, (устаревшая) класса [CComModule](../../atl/reference/ccommodule-class.md) в Visual C++ 6.0.  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#97](../../atl/codesnippet/cpp/patlmodule_1.cpp)]  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="see-also"></a>См. также  
 [Глобальные переменные](../../atl/reference/atl-global-variables.md)



