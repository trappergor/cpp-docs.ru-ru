---
title: "Метод HANDLETraits::Close | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9af70c2bc7b4c0829e7455d6389359618afb7232
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="handletraitsclose-method"></a>Метод HANDLETraits::Close
Закрывает указанный дескриптор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `h`  
 Чтобы закрыть дескриптор.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если обрабатывать `h` Закрыто успешно; в противном случае **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Структура HANDLETraits](../windows/handletraits-structure.md)