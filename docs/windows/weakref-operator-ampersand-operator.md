---
title: Оператор WeakRef::operator&amp; оператора | Документация Майкрософт
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
ms.openlocfilehash: 125ffe998e7c3f225f72e3fb47df4ef3525c37f9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649052"
---
# <a name="weakrefoperatoramp-operator"></a>Оператор WeakRef::operator&amp; оператор
Возвращает `ComPtrRef` , представляющий текущий **WeakRef** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&() throw()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект `ComPtrRef` , представляющий текущий **WeakRef** объекта.  
  
## <a name="remarks"></a>Примечания  
 Это внутренний вспомогательный оператор, который не предназначен для использования в коде.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс WeakRef](../windows/weakref-class.md)