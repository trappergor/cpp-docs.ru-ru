---
title: Оператор HStringReference::Operator&lt; оператора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
dev_langs:
- C++
ms.assetid: 55aa48e8-7c96-4123-9ebe-42b4cd8b9377
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 489d97252dcb4d20b7ef2f8557991a4e6016743d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605536"
---
# <a name="hstringreferenceoperatorlt-operator"></a>Оператор HStringReference::Operator&lt; оператор
Указывает, является ли первый параметр меньше значения второго параметра.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline bool operator<(  
    const HStringReference& lhs,   
    const HStringReference& rhs) throw()  
```  
  
### <a name="parameters"></a>Параметры  
 *lhs*  
 Первый параметр для сравнения. *LHS* можно ссылаться на **HStringReference**.  
  
 *правая часть*  
 Второй параметр для сравнения.  *правая часть* можно ссылаться на **HStringReference**.  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если *lhs* параметр меньше, чем *rhs* параметра; в противном случае **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HStringReference](../windows/hstringreference-class.md)