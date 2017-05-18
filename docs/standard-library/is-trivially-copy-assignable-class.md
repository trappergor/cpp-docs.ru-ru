---
title: "Класс is_trivially_copy_assignable | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_trivially_copy_assignable
- type_traits/std::is_trivially_copy_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_assignable
ms.assetid: 7410133e-f367-493f-92a7-e34e3ec5e879
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: 97935fed1736f111557a0cb86811a86d60505107
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="istriviallycopyassignable-class"></a>Класс is_trivially_copy_assignable
Проверяет, есть ли у типа тривиальный оператор присваивания копии.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Ty>
struct is_trivially_copy_assignable;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа содержит значение true, если тип `T` является классом, имеющим тривиальный оператор присваивания копии, в противном случае — значение false.  
  
 Конструктор присваивания для класса `T` является тривиальным, если он предоставляется неявно, класс `T` не имеет виртуальных функций, класс `T` не имеет виртуальных базовых классов, классы для всех нестатических членов класса типа "класс" имеют тривиальные операторы присваивания и классы для всех нестатических членов типа "массив классов" также имеют тривиальные операторы присваивания.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




