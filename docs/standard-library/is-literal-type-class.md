---
title: "Класс is_literal_type | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_literal_type
dev_langs: C++
helpviewer_keywords: is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aabb7d1c6e0c194f5d031e62d84753dfc0ded3d2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="isliteraltype-class"></a>Класс is_literal_type
Проверяет, можно ли использовать тип в качестве переменной `constexpr`, создавать его, использовать или возвращать из функций `constexpr`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
struct is_literal_type;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа имеет значение true, если тип `T` является *типом литерала*, в противном случае — значение false. Тип литерала — это `void`, скалярный тип, ссылочный тип, массив типа литерала или тип класса литерала. Тип класса литерала — это тип класса, который имеет тривиальный деструктор, составной тип или по крайней мере один конструктор `constexpr`, отличный от копирования и перемещения, и все его базовые классы и нестатические элементы данных являются неизменяемыми типами литералов. Хотя литерал всегда имеет тип литерала, концепция типа литерала включает в себя все, что компилятор может вычислить в качестве `constexpr` во время компиляции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)



