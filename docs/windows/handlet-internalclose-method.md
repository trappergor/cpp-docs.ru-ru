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
ms.openlocfilehash: 2190a8e85f81062cc1167aa844fccf4afc819bc9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648806"
---
# <a name="handletinternalclose-method"></a>Метод HandleT::InternalClose
Закрывает текущий **HandleT** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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