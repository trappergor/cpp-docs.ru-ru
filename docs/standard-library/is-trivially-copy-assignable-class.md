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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 0f8aad09e3ed083b9ffdd2199c9a9ab6462b840b
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

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




