---
title: Метод Implements::CastToUnknown | Документация Майкрософт
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
ms.openlocfilehash: a490e3b8dc620cb3f0f440b2e28cce1f2e69c76d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607252"
---
# <a name="implementscasttounknown-method"></a>Метод Implements::CastToUnknown
Возвращает указатель на базовый `IUnknown` интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Эта операция выполняется успешно и всегда возвращает `IUnknown` указатель.  
  
## <a name="remarks"></a>Примечания  
 Внутренняя вспомогательная функция.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Структура Implements](../windows/implements-structure.md)