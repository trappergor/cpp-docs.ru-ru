---
title: "Класс make_signed | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- make_signed
- type_traits/std::make_signed
dev_langs:
- C++
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
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
ms.openlocfilehash: 43b41b7016faeb593af12d01f940c27d00882b9e
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="makesigned-class"></a>Класс make_signed
Создает тип или наименьшей знаковый тип, размер которого больше или равен размеру типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип для изменения.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр модификатора типа содержит модифицированный тип, т. е. `T`, если `is_signed<T>` содержит значение true. В противном случае это наименьший тип без знака `UT` для которого `sizeof (T) <= sizeof (UT)`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




