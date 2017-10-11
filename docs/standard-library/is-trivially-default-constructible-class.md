---
title: "Класс is_trivially_default_constructible | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_trivially_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 9ad38fb23b5ac205a283969ea50041c1bfba2806
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="istriviallydefaultconstructible-class"></a>Класс is_trivially_default_constructible
Проверяет, есть ли у типа тривиальный конструктор по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Ty>
struct is_trivially_default_constructible;
```  
  
#### <a name="parameters"></a>Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа содержит значение true, если тип `Ty` является классом, имеющим тривиальный конструктор, в противном случае — значение false.  
  
 Конструктор по умолчанию для класса `Ty` является тривиальным, если:  
  
-   он является конструктором по умолчанию, объявленным неявно;  
  
-   класс `Ty` не имеет виртуальных функций;  
  
-   класс `Ty` не имеет виртуальных баз;  
  
-   все прямые базы класса `Ty` имеют тривиальные конструкторы;  
  
-   классы всех нестатических элементов данных типа класса имеют тривиальные конструкторы;  
  
-   классы всех нестатических элементов данных массива типов класса имеют тривиальные конструкторы.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




