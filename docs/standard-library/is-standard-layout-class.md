---
title: "Класс is_standard_layout | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_standard_layout
dev_langs:
- C++
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
caps.latest.revision: 16
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 41d0472a031904fbb40d381aa6113da17feb3e1b
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="isstandardlayout-class"></a>Класс is_standard_layout
Проверяет, является ли тип стандартным макетом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Ty>
struct is_standard_layout;
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Ty`|Запрашиваемый тип.|  
  
## <a name="remarks"></a>Примечания  
 Экземпляр этого предиката типа содержит значение true, если тип `Ty` является классом, имеющим стандартный макет объектов-членов; в противном случае — значение false.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




