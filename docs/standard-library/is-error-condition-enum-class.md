---
title: "Класс is_error_condition_enum | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_error_condition_enum
- system_error/std::is_error_condition_enum
dev_langs:
- C++
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 316e375554d80bfa58dfba537e5c36a881028a20
ms.lasthandoff: 02/24/2017

---
# <a name="iserrorconditionenum-class"></a>Класс is_error_condition_enum
Представляет тип предиката, проверяющий перечисление [error_condition](../standard-library/error-condition-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <_Enum>
class is_error_condition_enum;
```  
  
## <a name="remarks"></a>Примечания  
 Экземпляр этого [предиката типа](../standard-library/type-traits.md) содержит значение true, если тип `_Enum` является значением перечисления, подходящим для хранения в объекте типа `error_condition`.  
  
 Допускается добавление специализации в этот тип для определяемых пользователем типов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<system_error>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)   
 [<system_error>](../standard-library/system-error.md)




