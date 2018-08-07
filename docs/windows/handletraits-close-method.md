---
title: Метод HANDLETraits::Close | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 581c7b8447b800d9a3401cd76f3adc5ada25994d
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569834"
---
# <a name="handletraitsclose-method"></a>Метод HANDLETraits::Close
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
 [Структура HANDLETraits](../windows/handletraits-structure.md)