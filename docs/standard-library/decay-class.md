---
title: "Класс decay | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- decay
- std::decay
- type_traits/std::decay
dev_langs:
- C++
helpviewer_keywords:
- decay class
ms.assetid: 96baa2fd-c8e0-49af-be91-ba375ba7f9dc
caps.latest.revision: 20
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
ms.openlocfilehash: cb75f00c4f7dfc46122c8e69e5572de1ec23f8ed
ms.lasthandoff: 02/24/2017

---
# <a name="decay-class"></a>Класс decay
Создает тип, как передано по значению. Создает тип, не являющийся ссылочным, константным, временным, или создает указатель на тип из функции или типа массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>
struct decay;

template <class T>  
using decay_t = typename decay<T>::type;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип для изменения.  
  
## <a name="remarks"></a>Примечания  
 Используйте шаблон decay для создания результирующего типа, как если бы тип был передан по значению в качестве аргумента. Член класса шаблона typedef `type` содержит измененный тип, который определяется на следующих этапах:  
  
-   Тип `U` определяется как `remove_reference<T>::type`.  
  
-   Если `is_array<U>::value` имеет значение true, измененный тип `type` имеет значение `remove_extent<U>::type *`.  
  
-   Если же `is_function<U>::value` имеет значение true, измененный тип `type` имеет значение `add_pointer<U>::type`.  
  
-   В противном случае измененный тип `type` имеет значение `remove_cv<U>::type`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




