---
title: "Класс is_lvalue_reference | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_lvalue_reference
dev_langs: C++
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e095638f11ebf34181928d3708de62f8d0cf0289
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="islvaluereference-class"></a>Класс is_lvalue_reference
Проверяет, является ли тип ссылкой lvalue.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Ty>
struct is_lvalue_reference;
```  
  
#### <a name="parameters"></a>Параметры  
 `Ty`  
 Запрашиваемый тип.  
  
## <a name="remarks"></a>Примечания  
 Экземпляр этого предиката типа содержит значение true, если тип `Ty` является ссылкой на объект или функцию, в противном случае — значение false. Обратите внимание, что `Ty` не может быть ссылкой rvalue. Дополнительные сведения о rvalues см. в разделе [Оператор объявления ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)   
 [Значения Lvalues и Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)



