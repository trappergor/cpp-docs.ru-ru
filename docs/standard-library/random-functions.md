---
title: "Функции &lt;random&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3aebef535acb59046fab53d49051df16bd362c3c
ms.lasthandoff: 02/24/2017

---
# <a name="ltrandomgt-functions"></a>Функции &lt;random&gt;
  
##  <a name="generate_canonical"></a>  generate_canonical  
 Возвращает значение с плавающей запятой из случайной последовательности.  
  
> [!NOTE]
>  В стандарте ISO C++ указано, что эта функция должна возвращать значения в диапазоне [ `0`, `1`). Visual Studio еще не выполняет это требование. Для получения значений в этом диапазоне используйте [uniform_real_distribution](../standard-library/uniform-real-distribution-class.md).  
  
```  
template <class RealType, size_t Bits, class Generator>  
RealType generate_canonical(Generator& Gen);
```  
  
### <a name="parameters"></a>Параметры  
 `RealType`  
 Тип с плавающей запятой. Возможные типы см. в разделе [\<random>](../standard-library/random.md).  
  
 `Bits`  
 Генератор случайных чисел.  
  
 `Gen`  
 Генератор случайных чисел.  
  
### <a name="remarks"></a>Примечания  
 Функция шаблона повторно вызывает `operator()` класса `Gen` и преобразует возвращенные значения в значение с плавающей запятой `x` типа `RealType`, пока в `x` не будет получено указанное число разрядов мантиссы. Это число меньше значения `Bits` (которое не должно быть нулевым) и меньше полного количества разрядов мантиссы в `RealType`. Первый вызов предоставляет младшие разряды. Функция возвращает `x`.  
  
## <a name="see-also"></a>См. также  
 [\<random>](../standard-library/random.md)


