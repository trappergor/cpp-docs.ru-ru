---
title: Метод HandleT::InternalClose | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
dev_langs:
- C++
helpviewer_keywords:
- InternalClose method
ms.assetid: fe693c02-aa1f-4e00-8bdd-a0d7d736da0b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a54b61902c8994397c7bd6effa74a90d43c7e512
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39568645"
---
# <a name="handletinternalclose-method"></a>Метод HandleT::InternalClose
Закрывает текущий **HandleT** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
virtual bool InternalClose();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если текущий **HandleT** Закрыто успешно; в противном случае — значение **false**.  
  
## <a name="remarks"></a>Примечания  
 **InternalClose()** — **защищенные**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)