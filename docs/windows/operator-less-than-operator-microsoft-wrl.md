---
title: "оператор&lt; оператор (Microsoft::WRL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::operator<
dev_langs: C++
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d82291702791b138e0aaebefb5650e19d9e515f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="operatorlt-operator-microsoftwrl"></a>оператор&lt; оператор (Microsoft::WRL)
Определяет, является ли адрес один объект меньше другого.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<class T, class U>  
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();  
template<class T, class U>  
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `a`  
 Левый объект.  
  
 `b`  
 Правый объект.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true`Если адрес `a` меньше, чем адрес `b`; в противном случае `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)