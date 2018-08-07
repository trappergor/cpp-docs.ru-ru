---
title: Оператор HStringReference::Operator =-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs:
- C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc8f919dcec994be5d4f0300e9c96dde95895e16
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608525"
---
# <a name="hstringreferenceoperator-operator"></a>Оператор HStringReference::Operator=
Перемещает значение другого **HStringReference** объект с текущим **HStringReference** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HStringReference& operator=(HStringReference&& other) throw()  
```  
  
### <a name="parameters"></a>Параметры  
 *other*  
 Существующий **HStringReference** объекта.  
  
## <a name="remarks"></a>Примечания  
 Значение существующего *других* объект копируется в текущий **HStringReference** объекта, а затем *других* уничтожении объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)