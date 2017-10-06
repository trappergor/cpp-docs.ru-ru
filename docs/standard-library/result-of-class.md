---
title: "Класс result_of | Документы Майкрософт"
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
- type_traits/std::result_of
- type_traits/std::result_of_t
- type_traits/std::result_of::type
dev_langs:
- C++
helpviewer_keywords:
- std::result_of
- std::result_of_t
- std::result_of::type
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
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
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 08e4fc22725962d06bee35ed1adf63e3c9230ced
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="resultof-class"></a>Класс result_of
Определяет возвращаемый тип вызываемого типа, который принимает заданные типы аргументов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class>  
struct result_of; // Causes a static assert  
  
template <class Fn, class... ArgTypes>  
struct result_of<Fn(ArgTypes...)>;

// Helper type  
template<class T>
   using result_of_t = typename result_of<T>::type;
```  
  
#### <a name="parameters"></a>Параметры  
 `Fn`  
 Вызываемый тип для запроса.  
  
 `ArgTypes`  
 Типы списка аргументов к вызываемому типу для запроса.  
  
## <a name="remarks"></a>Примечания  
 Используйте этот шаблон, чтобы определить во время компиляции тип результата `Fn`(`ArgTypes`), где `Fn` — вызываемый тип либо ссылка на функцию или вызываемый тип, вызванные с помощью списка аргументов типов в `ArgTypes`. Член `type` класса шаблонов называет тип результата `decltype(std::invoke(declval<Fn>(), declval<ArgTypes>()...))`, если неоцененное выражение `std::invoke(declval<Fn>(), declval<ArgTypes>()...)` имеет правильный формат. В противном случае класс шаблона не имеет члена `type`. Тип `Fn` и все типы в пакете параметров `ArgTypes` должны быть полными типами, типами `void` или массивами с неизвестной границей.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




