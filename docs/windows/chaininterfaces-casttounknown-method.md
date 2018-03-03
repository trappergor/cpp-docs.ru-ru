---
title: "Метод ChainInterfaces::CastToUnknown | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: a6a58555-e5b0-4773-aba0-959d9d362c6b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3f49ca9eb6218e5dce42be5d951d134ad74745e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="chaininterfacescasttounknown-method"></a>Метод ChainInterfaces::CastToUnknown
Приводит указатель интерфейса типа, определяемого `I0` параметр шаблона в указатель на IUnknown.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс IUnknown.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Структура ChainInterfaces](../windows/chaininterfaces-structure.md)