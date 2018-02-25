---
title: "Класс make_unsigned | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::make_unsigned
dev_langs:
- C++
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3691e8840bf4d51f48359e7efbdd777bd18e01cb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="makeunsigned-class"></a>Класс make_unsigned
Создает тип или наименьший беззнаковый тип, размер которого больше или равен размеру типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание:|  
|---------------|-----------------|  
|`T`|Тип для изменения.|  
  
## <a name="remarks"></a>Примечания  
 Экземпляр модификатора типа содержит модифицированный тип, т. е. `T`, если `is_unsigned<T>` содержит значение true. В противном случае это наименьший тип со знаком `ST`, для которого `sizeof (T) <= sizeof (ST)`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)



