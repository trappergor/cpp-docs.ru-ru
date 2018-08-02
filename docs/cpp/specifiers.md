---
title: Спецификаторы | Документация Майкрософт
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
ms.openlocfilehash: 3d9898dc6b918643aa8ca4ace34ce2e716344c57
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463493"
---
# <a name="specifiers"></a>Спецификаторы
В этом разделе описывается *decl-specifiers* (описатели объявления) компонент [объявление](declarations-and-definitions-cpp.md).  
  
 Следующие местозаполнители и ключевые слова языка являются определителями объявления:  
  
 *спецификатор класса хранения*  
  
 *спецификатор типа*  
  
 *спецификатор функция*  
  
 [friend](../cpp/friend-cpp.md)  
  
 [typedef] ( [typedef](http://msdn.microsod) `(` *extended-decl-modifier-seq* `)`  
  
## <a name="remarks"></a>Примечания  
 *Decl-specifiers* часть объявления является самой длинной последовательностью *decl-specifiers* которая может использоваться для обозначения имени типа, не включая указателя или ссылки модификаторы. Остальная часть объявления является *декларатор*, включая представленное имя.  
  
 В следующей таблице перечислены четыре объявления, а затем каждое объявление *decl-specifers* и *декларатор* компонент отдельно.  
  
|Объявление|*Спецификаторы decl-*|`declarator`|  
|-----------------|------------------------|------------------|  
|`char *lpszAppName;`|**char**|`*lpszAppName`|  
|`typedef char * LPSTR;`|**char**|`*LPSTR`|  
|`const int func1();`|**const int**|`func1`|  
|`volatile void *pvvObj;`|**volatile void**|`*pvvObj`|  
  
 Так как **автоматический**, **без знака**, **long**, и **короткие** подразумевают **int**,  **TypeDef** имя одного из этих ключевых слов принимается является членом следующих *declarator-list,* не *decl-specifiers*.  
  
> [!NOTE]
>  Поскольку имя можно объявить повторно, его интерпретация относится к самой последней декларации в текущей области. Повторное объявление может повлиять на способ интерпретации имен компилятором, особенно **typedef** имена.  
  
## <a name="see-also"></a>См. также  
 [Объявления и определения](declarations-and-definitions-cpp.md)