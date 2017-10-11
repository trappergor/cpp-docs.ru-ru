---
title: "Функции &lt;vector&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords:
- std::swap [vector]
caps.latest.revision: 10
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 239ac662d19e3d0aa788e830557c28bc84835828
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="ltvectorgt-functions"></a>Функции &lt;vector&gt;

  
##  <a name="swap"></a>  swap  
 Меняет местами элементы двух векторов.  
  
```  
template <class Type, class Allocator>  
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Вектор, содержащий элементы, которые будут заменены, или вектор, элементы которого должны быть заменены на элементы вектора `left`.  
  
 `left`  
 Вектор, элементы которого должны поменяться местами с элементами вектора `right`.  
  
### <a name="remarks"></a>Примечания  
 Функция шаблона является алгоритмом, который специализируется на вектор класс контейнера для выполнения функции-члена `left`. [Vector::Swap](../standard-library/vector-class.md) *(правый*). Это экземпляры частичного упорядочивания шаблонов функций компилятором. Когда функции шаблона перегружаются таким образом, что соответствие шаблона и вызова функции не является уникальным, компилятор выберет наиболее специализированную версию функции шаблона. Общая версия функции-шаблона, **template** \< **class T**> **void swap**(**T&**, **T&**) в классе алгоритма работает с помощью назначения и выполняется медленно. Специализированная версия в каждом контейнере работает гораздо быстрее, так как она может работать с внутренним представлением класса контейнера.  
  
### <a name="example"></a>Пример  
  См. пример кода для функции-члена [vector::swap](../standard-library/vector-class.md), в котором используется версия шаблона `swap`.  
  
## <a name="see-also"></a>См. также  
 [\<vector>](../standard-library/vector.md)


