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
ms.openlocfilehash: 2ac723ed80eaebc4b3f245ef56b761600007cd2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028380"
---
# <a name="improper-access-to-a-union"></a>Неправильный доступ к объединению

**ANSI 3.3.2.3** Доступ к члену объекта объединения через члена другого типа

Если объявляется объединение двух типов и сохраняется одно значение, но для доступа к объединению используется другой тип, результаты будут ненадежными.

Например, объявлено объединение **float** и `int`. Сохраняется значение **float**, но программа позднее использует это значение как `int`. Полученное значение будет зависеть от типа внутреннего хранилища для значений **float**. Целочисленное значение будет ненадежным.

## <a name="see-also"></a>См. также

[Структуры, объединения, перечисления и битовые поля](../c-language/structures-unions-enumerations-and-bit-fields.md)