---
title: Оператор HString::Operator =-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
dev_langs:
- C++
ms.assetid: 8e68c1ff-bc57-4526-810e-af3c284b4e30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9cc496f4f1c23508b2ebba2788910ff9c9ca2066
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608603"
---
# <a name="hstringoperator-operator"></a>Оператор HString::Operator=
Перемещает значение другого **HString** объект с текущим **HString** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HString& operator=(HString&& other) throw()  
```  
  
### <a name="parameters"></a>Параметры  
 *other*  
 Существующий **HString** объекта.  
  
## <a name="remarks"></a>Примечания  
 Значение существующего *других* объект копируется в текущий **HString** объекта, а затем *других* уничтожении объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)