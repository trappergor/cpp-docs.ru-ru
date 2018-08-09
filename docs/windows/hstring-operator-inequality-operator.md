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
ms.openlocfilehash: e3fabc0dcbbc31a1707d1823fb1ec49a53aca6d3
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015879"
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
  
### <a name="parameters"></a>Параметры  
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