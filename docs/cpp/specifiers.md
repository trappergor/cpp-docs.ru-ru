---
title: "Спецификаторы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: c67ae6ce353ee48635df1b3be6b124344cdd4e91
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="specifiers"></a>Спецификаторы
В этом разделе описывается *спецификаторы decl* (описатели объявления) компонент [объявление](declarations-and-definitions-cpp.md).  
  
 Следующие местозаполнители и ключевые слова языка являются определителями объявления:  
  
 *спецификатор класса хранения*  
  
 *спецификатор типа*  
  
 *спецификатор функция*  
  
 [Friend](../cpp/friend-cpp.md)  
  
 [typedef](http://msdn.microsoft.com/en-us/cc96cf26-ba93-4179-951e-695d1f5fdcf1)  
  
 [__declspec](../cpp/declspec.md) `(` *расширенных последовательность модификаторов объявления*`)`  
  
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
