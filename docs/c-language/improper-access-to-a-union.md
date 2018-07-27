---
title: Неправильный доступ к объединению | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: b273d984-62a8-4003-9a87-bf0149d3f2dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c322ff9e411cc6c9ef845fdd9a289a9ed5c49d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383596"
---
# <a name="improper-access-to-a-union"></a>Неправильный доступ к объединению
**ANSI 3.3.2.3** Доступ к члену объекта объединения через члена другого типа  
  
 Если объявляется объединение двух типов и сохраняется одно значение, но для доступа к объединению используется другой тип, результаты будут ненадежными.  
  
 Например, объявлено объединение **float** и `int`. Сохраняется значение **float**, но программа позднее использует это значение как `int`. Полученное значение будет зависеть от типа внутреннего хранилища для значений **float**. Целочисленное значение будет ненадежным.  
  
## <a name="see-also"></a>См. также  
 [Структуры, объединения, перечисления и битовые поля](../c-language/structures-unions-enumerations-and-bit-fields.md)