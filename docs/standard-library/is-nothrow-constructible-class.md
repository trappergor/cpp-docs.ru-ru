---
title: "Класс is_nothrow_constructible | Документы Майкрософт"
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
- is_nothrow_constructible
- type_traits/std::is_nothrow_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
caps.latest.revision: 12
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: bf39b973c39fd024de6b4b75b3cc47aeb5bec9d8
ms.lasthandoff: 02/24/2017

---
# <a name="isnothrowconstructible-class"></a>Класс is_nothrow_constructible
Проверяет, является ли тип конструируемым и известным как не выдающим исключения при использовании указанных типов аргументов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T, class... Args>  
struct is_nothrow_constructible;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Запрашиваемый тип.  
  
 `Args`  
 Типы аргументов для сопоставления в конструкторе `T`.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа имеет значение true, если тип `T` — конструируемый при использовании типов аргументов в `Args`, и компилятор знает, что конструктор не выдает исключений, в противном случае — значение false. Тип `T` — конструируемый, если определение переменной `T t(std::declval<Args>()...);` имеет правильный формат. Как `T`, так и все типы в `Args`, должны быть полными типами, `void` либо массивами с неизвестной границей.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




