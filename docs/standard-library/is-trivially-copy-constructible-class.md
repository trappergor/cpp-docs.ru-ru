---
title: "Класс is_trivially_copy_constructible | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_trivially_copy_constructible
- type_traits/std::is_trivially_copy_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
caps.latest.revision: 24
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: a9f40518942be5632f13dee3865b603f04cbca84
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="istriviallycopyconstructible-class"></a>Класс is_trivially_copy_constructible
Проверяет, есть ли у типа тривиальный конструктор копии.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>
struct is_trivially_copy_constructible;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа содержит значение true, если тип `T` является классом, имеющим тривиальный конструктор копирования, в противном случае — значение false.  
  
 Конструктор копии для класса `T` является тривиальным, если он предоставляется неявно, класс `T` не имеет виртуальных функций или виртуальных базовых классов, все прямые базовые классы класса `T` имеют тривиальные конструкторы копий, классы для всех нестатических элементов данных типа "класс" имеют тривиальные конструкторы копий и классы для всех нестатических элементов данных типа "массив классов" также имеют тривиальные конструкторы копий.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




