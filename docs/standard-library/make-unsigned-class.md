---
title: "Класс make_unsigned | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- make_unsigned
- type_traits/std::make_unsigned
dev_langs:
- C++
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 28baed4badda4f2c1d7e5b20235fe8d40c2a7195
ms.openlocfilehash: 1bdebf2a3d3f03defa041d049ac98287df7aad6c
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

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
  
|Параметр|Описание|  
|---------------|-----------------|  
|`T`|Тип для изменения.|  
  
## <a name="remarks"></a>Примечания  
 Экземпляр модификатора типа содержит модифицированный тип, т. е. `T`, если `is_unsigned<T>` содержит значение true. В противном случае это наименьший тип со знаком `ST`, для которого `sizeof (T) <= sizeof (ST)`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




