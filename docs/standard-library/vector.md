---
title: "&lt;vector&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <vector>
- std.<vector>
- std::<vector>
dev_langs:
- C++
helpviewer_keywords:
- vector header
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
caps.latest.revision: 25
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 99aa5d5df1367dfb6e6f6c0b9333783240a12690
ms.lasthandoff: 02/24/2017

---
# <a name="ltvectorgt"></a>&lt;vector&gt;
Определяет вектор классов шаблонов контейнеров и некоторые вспомогательные шаблоны.  
  
 `vector` — это контейнер, который упорядочивает элементы данного типа в виде линейной последовательности. Он обеспечивает быстрый произвольный доступ к любому элементу и позволяет динамически добавлять элементы в последовательность и удалять их. `vector` является наиболее подходящим типом контейнера для последовательности, когда на первом месте стоит производительность произвольного доступа.  
  
 Подробнее о классе `vector` см. в разделе [Класс vector](../standard-library/vector-class.md). Сведения о специализации `vector<bool>` см. в разделе [Класс vector\<bool>](../standard-library/vector-bool-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace std {  
template <class Type, class Allocator>  
class vector;  
template <class Allocator>  
class vector<bool>;  
 
template <class Allocator>  
struct hash<vector<bool, Allocator>>;  
 // TEMPLATE FUNCTIONS  
template <class Type, class Allocator>  
bool operator== (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator!= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<(
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator> (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator<= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
bool operator>= (
    const vector<Type, Allocator>& left,  
    const vector<Type, Allocator>& right);

template <class Type, class Allocator>  
void swap (
    vector<Type, Allocator>& left,  
    vector<Type, Allocator>& right);

}  // namespace std  
```  
  
#### <a name="parameters"></a>Параметры  
 Тип  
 Параметр-шаблон для типа данных, хранящихся в векторе.  
  
 Allocator  
 Параметр-шаблон для хранимого объекта распределителя, отвечающего за выделение и освобождение памяти.  
  
 ` left`  
 Первый (левый) вектор в операции сравнения.  
  
 ` right`  
 Второй (правый) вектор в операции сравнения.  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор! =](../standard-library/vector-operators.md#operator_neq)|Проверяет следующее условие: объект вектора слева от оператора не равен объекту вектора справа от оператора.|  
|[оператор<](../standard-library/vector-operators.md#operator_lt_)|Проверяет следующее условие: объект вектора слева от оператора меньше, чем объект вектора справа от оператора.|  
|[оператор\<=](../standard-library/vector-operators.md#operator_lt__eq)|Проверяет следующее условие: объект вектора слева от оператора меньше или равен объекту вектора справа от оператора.|  
|[оператор==](../standard-library/vector-operators.md#operator_eq_eq)|Проверяет следующее условие: объект вектора слева от оператора равен объекту вектора справа от оператора.|  
|[оператор>](../standard-library/vector-operators.md#operator_gt_)|Проверяет следующее условие: объект вектора слева от оператора больше, чем объект вектора справа от оператора.|  
|[оператор>=](../standard-library/vector-operators.md#operator_gt__eq)|Проверяет следующее условие: объект вектора слева от оператора больше или равен объекту вектора справа от оператора.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс vector](../standard-library/vector-class.md)|Класс шаблона контейнеров последовательностей для хранения элементов заданного типа в линейном порядке и быстрого произвольного доступа к любому элементу.|  
  
### <a name="specializations"></a>Специализации  
  
|||  
|-|-|  
|[Класс vector\<bool>](../standard-library/vector-bool-class.md)|Полная специализация вектора шаблонного класса для элементов типа `bool` с распределителем для базового типа, используемого специализацией.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<vector>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)


