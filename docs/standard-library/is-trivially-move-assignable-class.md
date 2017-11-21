---
title: "Класс is_trivially_move_assignable | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_trivially_move_assignable
dev_langs: C++
helpviewer_keywords: is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 078d138126a432e3be0c2709b4ae351f2383ae44
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="istriviallymoveassignable-class"></a>Класс is_trivially_move_assignable
Проверяет, есть ли у типа тривиальный оператор присваивания перемещением.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Ty>
struct is_trivially_move_assignable;
```  
  
#### <a name="parameters"></a>Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа содержит значение true, если тип `Ty` является классом, имеющим тривиальный оператор присваивания перемещением, в противном случае — значение false.  
  
 Оператор присваивания перемещением для класса `Ty`, является тривиальным, если:  
  
 он неявно предоставляется;  
  
 класс `Ty` не имеет виртуальных функций;  
  
 класс `Ty` не имеет виртуальных баз;  
  
 классы всех нестатических элементов данных типа класса имеют тривиальные операторы присваивания перемещением;  
  
 классы всех нестатических элементов данных массива типов класса имеют тривиальные операторы присваивания перемещением.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)



