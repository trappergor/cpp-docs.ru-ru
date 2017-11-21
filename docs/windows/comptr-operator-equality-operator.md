---
title: "ComPtr::operator ==-оператор | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::operator==
dev_langs: C++
ms.assetid: 6a26e936-29d4-4b7d-b44a-7c575ad07509
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2f325e4dbdeb862b417d390bbc432917c67d7a94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="comptroperator-operator"></a>Оператор ComPtr::operator==
Определяет равенство двух объектов СomPtr.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
bool operator==(  
   const ComPtr<T>& a,  
   const ComPtr<U>& b  
);  
  
bool operator==(  
   const ComPtr<T>& a,  
   decltype(__nullptr)  
);  
  
bool operator==(  
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
 Первый оператор возвращает `true` Если объект `a` равен объекту `b`; в противном случае `false`.  
  
 Второй и третий операторы возвращают `true` Если объект `a` равен `nullptr`; в противном случае `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)   
 [Класс ComPtr](../windows/comptr-class.md)