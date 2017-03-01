---
title: "Класс underlying_type | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- underlying_type
- std.underlying_type
- std::underlying_type
- type_traits/std::underlying_type
dev_langs:
- C++
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
caps.latest.revision: 13
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
translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 95012fdeb3ac78d5e1cc76e03ed851a0b9701f5e
ms.lasthandoff: 02/24/2017

---
# <a name="underlyingtype-class"></a>Класс underlying_type
Создает базовый целочисленный тип для типа перечисления.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
struct underlying_type;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип для изменения.  
  
## <a name="remarks"></a>Примечания  
 Определение типа члена `type` для класса шаблона задает имя базового целочисленного типа `T`, где `T` имеет тип перечисления, в противном случае определение типа члена `type` отсутствует.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




