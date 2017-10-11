---
title: "Класс is_nothrow_default_constructible | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::is_nothrow_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_default_constructible
ms.assetid: c576fcc9-5be1-43aa-b93a-64d3f1848887
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 4ade369f00121d02b8cf60d50dba6b7552a3f605
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="isnothrowdefaultconstructible-class"></a>Класс is_nothrow_default_constructible
Проверяет, есть ли у типа невызывающий конструктор по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Ty>
struct is_nothrow_default_constructible;
```  
  
#### <a name="parameters"></a>Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр предиката типа содержит значение true, если тип `Ty` имеет конструктор nothrow по умолчанию, в противном случае — значение false. Экземпляр предиката типа эквивалентен `is_nothrow_constructible<Ty>`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)




