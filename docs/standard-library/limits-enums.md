---
title: "Перечисления &lt;limits&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: e0f4b6ca5d11207787f9ff4f27b21dbbc78080c0
ms.lasthandoff: 02/24/2017

---
# <a name="ltlimitsgt-enums"></a>Перечисления &lt;limits&gt;
|||  
|-|-|  
|[Перечисление float_denorm_style](#float_denorm_style_enumeration)|[Перечисление float_round_style](#float_round_style_enumeration)|  
  
##  <a name="a-namefloatdenormstyleenumerationa--floatdenormstyle-enumeration"></a><a name="float_denorm_style_enumeration"></a>  Перечисление float_denorm_style  
 Перечисление описывает различные методы, которые могут быть выбраны реализацией для представления ненормализованного значения с плавающей запятой, если оно мало для представления в качестве нормализованного значения:  
  
```
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Перечисление возвращает:  
  
- **denorm_indeterminate**, если не удается определить наличие или отсутствие денормализованных форм во время преобразования.  
  
- **denorm_absent**, если денормализованные формы отсутствуют.  
  
- **denorm_present**, если денормализованные формы присутствуют.  
  
### <a name="example"></a>Пример  
  См. раздел [numeric_limits::has_denorm](../standard-library/numeric-limits-class.md#numeric_limits__has_denorm) с примером, в котором можно получить доступ к значениям этого перечисления.  
  
##  <a name="a-namefloatroundstyleenumerationa--floatroundstyle-enumeration"></a><a name="float_round_style_enumeration"></a>  Перечисление float_round_style  
 Перечисление описывает различные методы, которые могут быть выбраны реализацией для округления значения с плавающей запятой до целочисленного.  
  
```
enum float_round_style {    
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Перечисление возвращает:  
  
- **round_indeterminate**, если метод округления определить не удается.  
  
- **round_toward_zero**, если округление к нолю.  
  
- **round_to_nearest**, если округление до ближайшего целого числа.  
  
- **round_toward_infinity**, если округление от ноля.  
  
- **round_toward_neg_infinity**, если округление к более отрицательному целому числу.  
  
### <a name="example"></a>Пример  
  См. раздел [numeric_limits::round_style](../standard-library/numeric-limits-class.md#numeric_limits__round_style) с примером, в котором можно получить доступ к значениям этого перечисления.  
  
## <a name="see-also"></a>См. также  
 [\<limits>](../standard-library/limits.md)




