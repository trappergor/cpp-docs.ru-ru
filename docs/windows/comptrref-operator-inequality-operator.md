---
title: "ComPtrRef::operator! =-оператор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef::operator!=
dev_langs: C++
ms.assetid: ab3093cc-6fbd-4039-890a-6df1cde992b6
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a61ed97ffd3caad6d254d3258711a7b45ad3c0dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="comptrrefoperator-operator"></a>Оператор ComPtrRef::operator!=
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   const Details::ComPtrRef<ComPtr<U>>& b  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   decltype(__nullptr)  
);  
  
bool operator!=(  
   decltype(__nullptr),  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
  
bool operator!=(  
   const Details::ComPtrRef<ComPtr<T>>& a,  
   void* b  
);  
  
bool operator!=(  
   void* b,  
   const Details::ComPtrRef<ComPtr<T>>& a  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `a`  
 Ссылка на объект ComPtrRef.  
  
 `b`  
 Ссылка на другой объект ComPtrRef или указатель на анонимный объект (`void*`).  
  
## <a name="return-value"></a>Возвращаемое значение  
 Первый оператор возвращает значение `true`, если объект `a` не равен объекту `b`; в противном случае —значение `false`.  
  
 Второй и третий операторы возвращают значение `true`, если объект `a` не равен `nullptr`; в противном случае — значение `false`.  
  
 Четвертый и пятый операторы yield `true` Если объект `a` не равен объекту `b`; в противном случае `false`.  
  
## <a name="remarks"></a>Примечания  
 Указывает на неравенство двух объектов ComPtrRef.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::wrl:: Details](../windows/microsoft-wrl-details-namespace.md)   
 [Класс ComPtrRef](../windows/comptrref-class.md)