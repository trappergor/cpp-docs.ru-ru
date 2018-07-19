---
title: Оператор WeakRef::operator&amp; оператор | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::operator&
dev_langs:
- C++
helpviewer_keywords:
- operator& operator
ms.assetid: 900afb73-3801-4d08-9b41-2e6a62011ccd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c8221b405618b1879f4e4c865115a227eb09857
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890122"
---
# <a name="weakrefoperatoramp-operator"></a>Оператор WeakRef::operator&amp; оператор
Возвращает объект ComPtrRef, представляющий текущий объект WeakRef.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&() throw()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект ComPtrRef, представляющий текущий объект WeakRef.  
  
## <a name="remarks"></a>Примечания  
 Это внутренний вспомогательный оператор, который не предназначен для использования в коде.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс WeakRef](../windows/weakref-class.md)