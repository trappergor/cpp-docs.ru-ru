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
ms.openlocfilehash: 5eddf38cddb3890be901fdc20f403521be146eb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073581"
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
