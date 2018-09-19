---
title: Ошибка компилятора C2891 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2891
dev_langs:
- C++
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86d81662cb02fa3c8f6af75009daf4dab9b70196
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016563"
---
# <a name="compiler-error-c2891"></a>Ошибка компилятора C2891

«параметр»: невозможно получить адрес параметра шаблона

Невозможно получить адрес параметра шаблона, если он не является ссылкой lvalue. Параметры типа не являются значениями lvalue, так как они имеют адрес не. Не являющиеся типом значения в списках параметров шаблона, которые не являются значениями, кроме того, не имеют адреса. Это пример кода, в результате Ошибка компилятора C2891, так как значение, передаваемое как параметр шаблона представляет собой созданный компилятором копию аргумента шаблона.

```
template <int i> int* f() { return &i; }
```

Параметры шаблона, которые являются значениями lvalue, такие как ссылочные типы, можно их адреса предприняли.

```
template <int& r> int* f() { return &r; }
```

Чтобы исправить эту ошибку, не получить адрес параметра шаблона, если это значение.