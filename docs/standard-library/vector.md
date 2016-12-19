---
title: "&lt; vector &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<vector>"
  - "std.<vector>"
  - "std::<vector>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector - заголовок"
ms.assetid: c1431ad8-c0b6-4dbb-89c4-5f651e432d7f
caps.latest.revision: 25
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; vector &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет вектор классов шаблонов контейнеров и некоторые вспомогательные шаблоны.  
  
 `vector` — это контейнер, который упорядочивает элементы данного типа в виде линейной последовательности. Он обеспечивает быстрый произвольный доступ к любому элементу и позволяет динамически добавлять элементы в последовательность и удалять их. `vector` является наиболее подходящим типом контейнера для последовательности, когда на первом месте стоит производительность произвольного доступа.  
  
 Дополнительные сведения о классе `vector`, в разделе [класс vector](vector%20Class.md). Сведения о специализации `vector<bool>`, в разделе [vector \< bool> класса](../Topic/vector%3Cbool%3E%20Class.md).  
  
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
|[оператор! =](../Topic/%3Cvector%3E%20operators.md#operator_neq)|Проверяет следующее условие: объект вектора слева от оператора не равен объекту вектора справа от оператора.|  
|[оператор <](../Topic/%3Cvector%3E%20operators.md#operator_lt_)|Проверяет следующее условие: объект вектора слева от оператора меньше, чем объект вектора справа от оператора.|  
|[оператор \< =](../Topic/%3Cvector%3E%20operators.md#operator_lt__eq)|Проверяет следующее условие: объект вектора слева от оператора меньше или равен объекту вектора справа от оператора.|  
|[оператор ==](../Topic/%3Cvector%3E%20operators.md#operator_eq_eq)|Проверяет следующее условие: объект вектора слева от оператора равен объекту вектора справа от оператора.|  
|[оператор >](../Topic/%3Cvector%3E%20operators.md#operator_gt_)|Проверяет следующее условие: объект вектора слева от оператора больше, чем объект вектора справа от оператора.|  
|[оператор > =](../Topic/%3Cvector%3E%20operators.md#operator_gt__eq)|Проверяет следующее условие: объект вектора слева от оператора больше или равен объекту вектора справа от оператора.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[Класс Vector](vector%20Class.md)|Класс шаблона контейнеров последовательностей для хранения элементов заданного типа в линейном порядке и быстрого произвольного доступа к любому элементу.|  
  
### <a name="specializations"></a>Специализации  
  
|||  
|-|-|  
|[Vector \< bool> класса](../Topic/vector%3Cbool%3E%20Class.md)|Полная специализация вектора шаблонного класса для элементов типа `bool` с распределителем для базового типа, используемого специализацией.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< vector>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Библиотека стандартных шаблонов](../misc/standard-template-library.md)

