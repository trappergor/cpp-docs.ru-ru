---
title: Метод Implements::CastToUnknown | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 857d13736a92bbbc2c6f1228b3444081ffc18de5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874490"
---
# <a name="implementscasttounknown-method"></a>Метод Implements::CastToUnknown
Возвращает указатель на базовый интерфейс IUnknown.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Эта операция всегда завершается успешно и возвращает указатель на IUnknown.  
  
## <a name="remarks"></a>Примечания  
 Внутренняя вспомогательная функция.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Структура Implements](../windows/implements-structure.md)