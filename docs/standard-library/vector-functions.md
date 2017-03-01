---
title: "Функции &lt;vector&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: bb62c0c4e5b2965438539b17ec5a2c465e647ed7
ms.lasthandoff: 02/24/2017

---
# <a name="ltvectorgt-functions"></a>Функции &lt;vector&gt;

  
##  <a name="a-nameswapa--swap"></a><a name="swap"></a>  swap  
 Меняет местами элементы двух векторов.  
  
```  
template <class Type, class Allocator>  
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Вектор, содержащий элементы, которые будут заменены, или вектор, элементы которого должны быть заменены на элементы вектора ` left`.  
  
 ` left`  
 Вектор, элементы которого должны поменяться местами с элементами вектора ` right`.  
  
### <a name="remarks"></a>Примечания  
 Функция шаблона является алгоритмом, который специализируется на векторе класса контейнера для выполнения функции-члена ` left.` [vector::swap](../standard-library/vector-class.md) *( right*). Это экземпляры частичного упорядочивания шаблонов функций компилятором. Когда функции шаблона перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции шаблона. Общая версия функции-шаблона, **template** \< **class T**> **void swap**(**T&**, **T&**) в классе алгоритма работает с помощью назначения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
### <a name="example"></a>Пример  
  См. пример кода для функции-члена [vector::swap](../standard-library/vector-class.md), в котором используется версия шаблона `swap`.  
  
## <a name="see-also"></a>См. также  
 [\<vector>](../standard-library/vector.md)


