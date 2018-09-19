---
title: Ошибка компилятора C2040 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2040
dev_langs:
- C++
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccfbacff97550e20c0dd0202e0737585ffd39d6d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46016472"
---
# <a name="compiler-error-c2040"></a>Ошибка компилятора C2040

operator: identifier1 отличается по уровням косвенного обращения от identifier2

Выражение, включающее заданные операнды, содержит несовместимые или неявно преобразованные типы операндов. Если оба операнда арифметические или неарифметические (например, массив или указатель), они используются без изменения. Если один из операндов арифметический, а другой — нет, арифметический операнд преобразуется в неарифметический.

В этом примере показано возникновение ошибки C2040 и приводятся сведения по ее устранению.

```
// C2040.cpp
// Compile by using: cl /c /W3 C2040.cpp
bool test() {
   char c = '3';
   return c == "3"; // C2446, C2040
   // return c == '3'; // OK
}
```