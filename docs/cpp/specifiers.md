---
title: Спецификаторы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2888f8a75e9b7addd2b8f195ffbf875c2b7ae1a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="specifiers"></a>Спецификаторы
В этом разделе описывается *спецификаторы decl* (описатели объявления) компонент [объявление](declarations-and-definitions-cpp.md).  
  
 Следующие местозаполнители и ключевые слова языка являются определителями объявления:  
  
 *спецификатор класса хранения*  
  
 *спецификатор типа*  
  
 *спецификатор функция*  
  
 [friend](../cpp/friend-cpp.md)  
  
 [typedef](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1)  
  
 [__declspec](../cpp/declspec.md) `(` *расширенных последовательность модификаторов объявления* `)`  
  
## <a name="remarks"></a>Примечания  
 *Спецификаторы decl* часть объявления является самой длинной последовательностью *спецификаторы decl* , можно предпринять для обозначения имени типа, не включая указателя или ссылки модификаторы. Остальная часть объявления является *декларатор*, включающее имя появились.  
  
 В следующей таблице представлены четыре объявления и затем перечисляет каждое объявление *decl-specifers* и *декларатор* компонент отдельно.  
  
|Объявление|*Спецификаторы объявления*|`declarator`|  
|-----------------|------------------------|------------------|  
|`char *lpszAppName;`|`char`|`*lpszAppName`|  
|`typedef char * LPSTR;`|`char`|`*LPSTR`|  
|`const int func1();`|`const int`|`func1`|  
|`volatile void *pvvObj;`|`volatile void`|`*pvvObj`|  
  
 Поскольку `signed`, `unsigned`, `long`, и `short` подразумевают `int`, `typedef` имя одного из этих ключевых слов, принимается в является членом следующих *список деклараторов* , отличного от *спецификаторы decl*.  
  
> [!NOTE]
>  Поскольку имя можно объявить повторно, его интерпретация относится к самой последней декларации в текущей области. Повторное объявление может повлиять на способ интерпретации имен компилятором, в особенности — имен `typedef`.  
  
## <a name="see-also"></a>См. также  
 [Объявления и определения](declarations-and-definitions-cpp.md)