---
title: Метод HANDLENullTraits::Close | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 6fb2fa0d-df20-45dc-856f-f78497f8bdf9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c3bc6e7adfa99e2ce25c9913309b5c5bd486bee0
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569405"
---
# <a name="handlenulltraitsclose-method"></a>Метод HANDLENullTraits::Close
Закрывает указанный дескриптор.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *h*  
 Чтобы закрыть дескриптор.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если обрабатывать *h* Закрыто успешно; в противном случае — значение **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Структура HANDLENullTraits](../windows/handlenulltraits-structure.md)