---
title: Спецификаторы
ms.date: 11/04/2016
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
ms.openlocfilehash: aef967b26321f289cb8c7bd0402d7fe8f12b77b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611410"
---
# <a name="specifiers"></a>Спецификаторы

В этом разделе описывается *decl-specifiers* (описатели объявления) компонент [объявление](declarations-and-definitions-cpp.md).

Следующие местозаполнители и ключевые слова языка являются определителями объявления:

*спецификатор класса хранения*

*спецификатор типа*

*спецификатор функция*

[friend](friend-cpp.md)

[TypeDef](aliases-and-typedefs-cpp.md) `(` *extended-decl-modifier-seq* `)`

[__declspec](declspec.md) `(` *extended-decl-modifier-seq* `)`

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
