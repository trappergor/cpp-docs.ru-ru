---
title: Метод HandleT::InternalClose | Документы Microsoft
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
ms.openlocfilehash: 7b0aef97645d515a03dcf2cab90eedc06f07971c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874149"
---
# <a name="handletinternalclose-method"></a>Метод HandleT::InternalClose
Закрытие текущего объекта HandleT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
virtual bool InternalClose();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` Если текущего объекта HandleT Закрыто успешно. в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 InternalClose() защищен.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)