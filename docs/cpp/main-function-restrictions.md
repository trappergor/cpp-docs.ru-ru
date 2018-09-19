---
title: Ограничения функции Main | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Main
dev_langs:
- C++
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93f5cce15d4db9f7f6d4e3361d22028fccd676f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117365"
---
# <a name="main-function-restrictions"></a>Ограничения функции main

Несколько ограничений **основной** функцию, которая не применяются для любых других функций C++. **Основной** функции:

- Не может быть перегружен (см. в разделе [перегрузка функций](function-overloading.md)).

- Не могут объявляться как **встроенного**.

- Не могут объявляться как **статических**.

- Нельзя получить ее адрес.

- Вызвать невозможно.

## <a name="see-also"></a>См. также

[Функция main: запуск программы](../cpp/main-program-startup.md)