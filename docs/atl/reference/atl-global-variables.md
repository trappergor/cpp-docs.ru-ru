---
title: Глобальные переменные ATL | Документы Microsoft
ms.custom: ''
ms.date: 12/06/2017
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ATLBASE/_pAtlModule
dev_langs:
- C++
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4664c99eb49b57f258be399c042fa14b60bbecdf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="atl-global-variables"></a>Глобальные переменные библиотеки ATL

## <a name="patlmodule"></a>_pAtlModule  
Глобальная переменная сохранения указателя к текущему модулю.  

```cpp  
__declspec(selectany) CAtlModule * _pAtlModule  
```  
### <a name="remarks"></a>Примечания  
Методы в этой глобальной переменной можно использовать для предоставления функциональных возможностей, предоставленный класс (устаревшая) CComModule в Visual C++ 6.0.

### <a name="example"></a>Пример  

```cpp  
LONG lLocks = _pAtlModule->GetLockCount();  
```  
### <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  

