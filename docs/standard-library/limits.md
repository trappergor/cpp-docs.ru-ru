---
title: "&lt;limits&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<limits>
- std::<limits>
- limits/std::<limits>
- <limits>
dev_langs:
- C++
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 86978cd4549f0672dac7cad0e4713380ea189c27
ms.openlocfilehash: bd4d0e1dbc7b350cd0683fdd5e6ad3fc1dc1f781
ms.contentlocale: ru-ru
ms.lasthandoff: 04/18/2017

---
# <a name="ltlimitsgt"></a>&lt;limits&gt;
Определяет класс шаблона `numeric_limits` и два перечисления, касающиеся представления значений с плавающей запятой и округления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <limits>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Явные специализации класса `numeric_limits` описывают множество свойств базовых типов, включая включая символьные типа, целочисленные типы, типы с плавающей запятой и `bool`, определяемые реализацией, а не фиксированными правилами языка C++. Свойства, описанные в \<limits>, включают точность, представления минимального и максимального размера, округление и сообщение об ошибках типа.  
  
### <a name="enumerations"></a>Перечисления  
  
|||  
|-|-|  
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|Перечисление описывает различные методы, которые могут быть выбраны реализацией для представления ненормализованного значения с плавающей запятой, если оно мало для представления в качестве нормализованного значения:|  
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|Перечисление описывает различные методы, которые могут быть выбраны реализацией для округления значения с плавающей запятой до целочисленного.|  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[numeric_limits Class](../standard-library/numeric-limits-class.md)|Класс шаблона описывает арифметические свойства встроенных числовых типов.|  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




