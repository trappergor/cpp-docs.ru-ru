---
title: Оператор HString::Operator! =-оператор | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator!=
dev_langs:
- C++
ms.assetid: dcdd2aca-e7d6-4bf1-b2de-03efbb430a93
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e35c0b9c448ce9b7aeb6e5f14627e82274a72a41
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39604477"
---
# <a name="hstringoperator-operator"></a>Оператор HString::Operator!=
Указывает, действительно ли два параметра не равны.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline bool operator!=( const HString& lhs,   
                        const HString& rhs) throw()  
  
inline bool operator!=( const HStringReference& lhs,   
                        const HString& rhs) throw()  
  
inline bool operator!=( const HString& lhs,   
                        const HStringReference& rhs) throw()  
  
inline bool operator!=( const HSTRING& lhs,   
                        const HString& rhs) throw()  
  
inline bool operator!=( const HString& lhs,   
                        const HSTRING& rhs) throw()  
```  
  
#### <a name="parameters"></a>Параметры  
 *lhs*  
 Первый параметр для сравнения. *LHS* может быть **HString** или `HStringReference` объекта или дескриптором HSTRING.  
  
 *правая часть*  
 Второй параметр для сравнения. *rhs* может быть **HString** или `HStringReference` объекта или дескриптором HSTRING.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если *lhs* и *rhs* параметры не равны; в противном случае — значение **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HString](../windows/hstring-class.md)