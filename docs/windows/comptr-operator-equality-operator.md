---
title: Оператор ComPtr::operator ==-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator==
dev_langs:
- C++
ms.assetid: 6a26e936-29d4-4b7d-b44a-7c575ad07509
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9750f0d49f4c7a580b2c99d0c833c5381ba20997
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467343"
---
# <a name="comptroperator-operator"></a>Оператор ComPtr::operator==
Указывает ли два **ComPtr** объекты равны.  
  
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
 *a*  
 Ссылку на **ComPtr** объекта.  
  
 *b*  
 Ссылка на другой **ComPtr** объекта.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Первый оператор возвращает **true** Если объект *a* равен объекту *b*; в противном случае **false**.  
  
 Второй и третий операторы возвращают **true** Если объект *a* равен **nullptr**; в противном случае **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)   
 [Класс ComPtr](../windows/comptr-class.md)