---
title: "Класс aligned_union | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::aligned_union
dev_langs:
- C++
helpviewer_keywords:
- aligned_union
ms.assetid: 9931a44d-3a67-4f29-a0f6-d47a7cf560ac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 10f729463bca1325617831c3d558048416e105e2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="alignedunion-class"></a>Класс aligned_union
Предоставляет достаточно большой и должным образом выровненный тип POD для хранения типа объединения и требуемого размера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <std::size_t Len, class... Types>  
struct aligned_union;  
 
template <std::size_t Len, class... Types>  
using aligned_union_t = typename aligned_union<Len, Types...>::type;  
```  
  
#### <a name="parameters"></a>Параметры  
 `Len`  
 Значение выравнивания для самого крупного типа в объединении.  
  
 `Types`  
 Различные типы в базовом объединении.  
  
## <a name="remarks"></a>Примечания  
 Используйте этот класс шаблона для получения выравнивания и размера, необходимого для хранения объединения в неинициализированном хранилище. Член typedef `type` именует тип POD, подходящий для хранения любого типа из перечисленных в `Types`; минимальный размер — `Len`. Статический член `alignment_value` типа `std::size_t` содержит строгое выравнивание, необходимое для всех типов, перечисленных в `Types`.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать `aligned_union` для выделения буфера выровненного стека для размещения объединения.  
  
```  
// std__type_traits__aligned_union.cpp  
#include <iostream>  
#include <type_traits>  
  
union U_type  
{  
    int i;  
    float f;  
    double d;  
    U_type(float e) : f(e) {}  
};  
  
typedef std::aligned_union<16, int, float, double>::type aligned_U_type;  
  
int main()  
{  
    // allocate memory for a U_type aligned on a 16-byte boundary  
    aligned_U_type au;  
    // do placement new in the aligned memory on the stack  
    U_type* u = new (&au) U_type(1.0f);  
    if (nullptr != u)  
    {  
        std::cout << "value of u->i is " << u->i << std::endl;  
        // must clean up placement objects manually!  
        u->~U_type();  
    }  
}  
```  
  
```Output  
value of u->i is 1065353216  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<type_traits>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [<type_traits>](../standard-library/type-traits.md)   
 [Класс alignment_of](../standard-library/alignment-of-class.md)
