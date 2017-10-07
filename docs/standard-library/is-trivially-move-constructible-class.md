---
title: "Класс is_trivially_move_constructible | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_trivially_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_constructible
ms.assetid: 740bdec7-65e5-47b3-b94f-a2479ceac3ec
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: d59ca4d7830940a2b99e4e10e885d80842dc7d1b
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="istriviallymoveconstructible-class"></a>Класс is_trivially_move_constructible
Проверяет, есть ли у типа тривиальный конструктор перемещения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Ty>
struct is_trivially_move_constructible;
```  
  
#### <a name="parameters"></a>Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа содержит значение true, если тип `Ty` является классом, имеющим тривиальный конструктор перемещения, в противном случае — значение false.  
  
 Конструктор перемещения для класса `Ty` является тривиальным, если:  
  
 он неявно объявлен;  
  
 его типы параметров эквивалентны типам неявного объявления;  
  
 класс `Ty` не имеет виртуальных функций;  
  
 класс `Ty` не имеет виртуальных баз;  
  
 класс не содержит изменчивых нестатических элементов данных;  
  
 все прямые базы класса `Ty` имеют тривиальные конструкторы перемещения;  
  
 классы всех нестатических элементов данных типа класса имеют тривиальные конструкторы перемещения;  
  
 классы всех нестатических элементов данных массива типов класса имеют тривиальные конструкторы перемещения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




