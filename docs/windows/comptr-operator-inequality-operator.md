---
title: ComPtr::operator! =-оператор | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator!=
dev_langs:
- C++
ms.assetid: 63647240-dec7-4eb9-9272-96c07d01493c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2450b5d473d1caadae171516cf337479bfd5d603
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881885"
---
# <a name="comptroperator-operator"></a>Оператор ComPtr::operator!=
Определяет неравенство двух объектов СomPtr.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
bool operator!=(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator!=(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const ComPtr<T>& a  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `a`  
 Ссылка на объект ComPtr.  
  
 `b`  
 Ссылка на другой объект ComPtr.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Первый оператор возвращает значение `true`, если объект `a` не равен объекту `b`; в противном случае —значение `false`.  
  
 Второй и третий операторы возвращают значение `true`, если объект `a` не равен `nullptr`; в противном случае — значение `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)   
 [Класс ComPtr](../windows/comptr-class.md)