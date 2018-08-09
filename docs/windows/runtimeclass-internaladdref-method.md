---
title: Метод RuntimeClass::InternalAddRef | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::InternalAddRef
dev_langs:
- C++
helpviewer_keywords:
- InternalAddRef method
ms.assetid: b8ed7f93-83d8-47ec-988c-98fe65104e7a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 925ebb50c571c37d5137a24539429d75469a5f9b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010755"
---
# <a name="runtimeclassinternaladdref-method"></a>Метод RuntimeClass::InternalAddRef
Увеличивает счетчик ссылок для текущего **RuntimeClass** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
ULONG InternalAddRef();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Итоговый счетчик ссылок.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс RuntimeClass](../windows/runtimeclass-class.md)