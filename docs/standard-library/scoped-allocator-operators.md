---
title: "Операторы &lt;scoped_allocator&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scoped_allocator/std::operator!=
- scoped_allocator/std::operator==
dev_langs: C++
ms.assetid: 4dfe0805-cc6e-479f-887f-a1c164f73837
caps.latest.revision: "10"
manager: ghogen
ms.openlocfilehash: d29a5a99f261776468364717a13b90a1ddde5216
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ltscopedallocatorgt-operators"></a>Операторы &lt;scoped_allocator&gt;
|||  
|-|-|  
|[оператор!=](#op_neq)|[оператор==](#op_eq_eq)|  
  
##  <a name="op_neq"></a>  оператор!=  
 Сравнивает два объекта `scoped_allocator_adaptor`, чтобы определить их неравенство.  
  
```cpp  
template <class Outer, class... Inner>  
bool operator!=(
    const scoped_allocator_adaptor<Outer, Inner...>& left,  
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;  
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Левый объект `scoped_allocator_adaptor`.  
  
 `right`  
 Правой объект `scoped_allocator_adaptor`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `!(left == right)`  
  
##  <a name="op_eq_eq"></a>  оператор==  
 Сравнивает два объекта `scoped_allocator_adaptor`, чтобы определить, равны ли они.  
  
```cpp  
template <class Outer, class... Inner>  
bool operator==(
    const scoped_allocator_adaptor<Outer, Inner...>& left,  
    const scoped_allocator_adaptor<Outer, Inner...>& right) noexcept;  
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Левый объект `scoped_allocator_adaptor`.  
  
 `right`  
 Правой объект `scoped_allocator_adaptor`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `left.outer_allocator() == right.outer_allocator() && left.inner_allocator() == right.inner_allocator()`  
  
## <a name="see-also"></a>См. также  
 [<scoped_allocator>](../standard-library/scoped-allocator.md)

