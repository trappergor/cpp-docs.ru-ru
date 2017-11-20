---
title: "Класс Platform::Collections:: backinsertiterator | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: COLLECTION/Platform::Collections::BackInsertIterator::BackInsertIterator
dev_langs: C++
helpviewer_keywords: BackInsertIterator Class
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 197c0c8dc7de6dca562d961635706a51fff992c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="platformcollectionsbackinsertiterator-class"></a>Класс Platform::Collections::BackInsertIterator
Представляет итератор, который вставляет, а не перезаписывает элементы в конец упорядоченной коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <typename T>  
class BackInsertIterator : 
public ::std::iterator<::std::output_iterator_tag, void, void, void, void>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип элемента в текущей коллекции.  
  
### <a name="remarks"></a>Примечания  
 Класс BackInsertIterator реализует правила, необходимые для [back_insert_iterator Class](../standard-library/back-insert-iterator-class.md).  
  
### <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[BackInsertIterator::BackInsertIterator](#ctor)|Инициализирует новый экземпляр класса BackInsertIterator.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор BackInsertIterator::operator*](#operator-dereference)|Получает ссылку на текущий объект BackInsertIterator.|  
|[Оператор BackInsertIterator::operator++](#operator-increment)|Возвращает ссылку на текущий объект BackInsertIterator. Итератор не изменяется.|  
|[Оператор BackInsertIterator::operator=](#operator-assign)|Добавляет указанный объект в конец текущей упорядоченной коллекции.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `BackInsertIterator`  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
---
## <a name="ctor"></a>Конструктор BackInsertIterator::BackInsertIterator
Инициализирует новый экземпляр класса `BackInsertIterator`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
explicit BackInsertIterator(  
   Windows::Foundation::Collections::IVector<T>^ v);  
```  
  
#### <a name="parameters"></a>Параметры  
 `v`  
 IVector\<T > объекта.  
  
### <a name="remarks"></a>Примечания  
 `BackInsertIterator` вставляет элементы после последнего элемента объекта, указанного параметром `v`.  
 
## <a name="operator-assign"></a>BackInsertIterator::operator =-оператор
Добавляет указанный объект в конец текущей упорядоченной коллекции.  
  
## <a name="syntax"></a>Синтаксис  
  
```    
BackInsertIterator& operator=( const T& t);  
```  
  
#### <a name="parameters"></a>Параметры  
 `t`  
 Объект, добавляемый к текущей коллекции.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на текущий объект BackInsertIterator.  

## <a name="operator-dereference"></a>BackInsertIterator::operator *-оператор
Получает ссылку на текущий объект BackInsertIterator.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
BackInsertIterator& operator*();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на текущий объект BackInsertIterator.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор возвращает ссылку на текущий BackInsertIterator, а не на любой элемент в текущей коллекции.  
 
## <a name="operator-increment"></a>BackInsertIterator::operator ++-оператор
Возвращает ссылку на текущий объект BackInsertIterator. Итератор не изменяется.  
  
## <a name="syntax"></a>Синтаксис  
  
``` 
  
BackInsertIterator& operator++();  
  
BackInsertIterator operator++(int);  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на текущий объект BackInsertIterator.  
  
### <a name="remarks"></a>Примечания  
 Выражение в первом примере синтаксиса увеличивает значение текущего элемента BackInsertIterator перед его использованием, а во втором — после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.  
  
 Впрочем, этот оператор не изменяет объект BackInsertIterator. Вместо этого он возвращает ссылку на текущий итератор, остающийся неизменным. Это поведение аналогично [оператор *](#dereference-operator).  
  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](platform-namespace-c-cx.md)