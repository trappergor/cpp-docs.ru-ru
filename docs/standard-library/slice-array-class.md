---
title: "Класс slice_array | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: valarray/std::slice_array
dev_langs: C++
helpviewer_keywords: slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e87631a98e56adda0f7c6eed172546e9f17f45b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="slicearray-class"></a>Класс slice_array
Внутренний, вспомогательный класс шаблона, который поддерживает объекты срезов, предоставляя операции между массивами подмножеств, заданные срезом valarray.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Type>  
class slice_array : public slice {  
public:  
    typedef Type value_type;  
    void operator=(const valarray<Type>& x) const;

 
    void operator=(const Type& x) const;

 
    void operator*=(const valarray<Type>& x) const;

 
    void operator/=(const valarray<Type>& x) const;

 
    void operator%=(const valarray<Type>& x) const;

 
    void operator+=(const valarray<Type>& x) const;

 
    void operator-=(const valarray<Type>& x) const;

 
    void operator^=(const valarray<Type>& x) const;

 
    void operator&=(const valarray<Type>& x) const;

 
    void operator|=(const valarray<Type>& x) const;

 
    void operator<<=(const valarray<Type>& x) const;

 
    void operator>>=(const valarray<Type>& x) const;

 
// The rest is private or implementation defined  
}  
```  
  
## <a name="remarks"></a>Примечания  
 Класс описывает объект, который хранит ссылку на объект класса [valarray](../standard-library/valarray-class.md)**\<Type>** вместе с объектом класса [slice](../standard-library/slice-class.md), который описывает последовательность элементов для выбора из объекта **valarray\<Type**.  
  
 Класс шаблона создается неявно с помощью определенных операций valarray и не может использоваться непосредственно в программе. Оператор индекса среза использует внутренний вспомогательный класс шаблона:  
  
 `slice_array`\< **Type**> `valarray`< **Type**:: `operator[]` ( `slice`).  
  
 Объект **slice_array\<Type>** создается только путем записи выражения в форме [va&#91;sl&#93;](../standard-library/valarray-class.md#op_at) для среза **sl** класса valarray **va**. После этого функции-члены класса slice_array ведут себя как соответствующие сигнатуры функций, заданные для **valarray\<Type>** с той разницей, что затрагивается только последовательность выбранных элементов. Последовательность, управляемая классом slice_array, определяется тремя параметрами конструктора среза: индексом первого элемента в срезе, количеством элементов и расстоянием между элементами. Массив slice_array, вырезанный из класса valarray **va**, который объявлен **va**[ `slice`(2, 5, 3)], выбирает элементы с индексами 2, 5, 8, 11 и 14 из **va**. Чтобы процедура была действительной, индексы должны быть действительными.  
  
## <a name="example"></a>Пример  
 Пример объявления и использования класса slice_array см. в разделе [slice::slice](../standard-library/slice-class.md#slice).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<valarray>  
  
 **Пространство имен:** std  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

