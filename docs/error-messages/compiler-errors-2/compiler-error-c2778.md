---
title: Ошибка компилятора C2778 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2778
dev_langs:
- C++
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6106832ea82531a6f6915417ac56d53504db882e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022166"
---
# <a name="compiler-error-c2778"></a>Ошибка компилятора C2778

неправильно сформированный GUID в __declspec(uuid())

Передан неверный GUID [uuid](../../cpp/uuid-cpp.md) расширенный атрибут.

Идентификатор GUID должен быть строкой шестнадцатеричных чисел в следующем формате:

```
// C2778a.cpp
// compile with: /c
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};
```

`uuid` Расширенный атрибут принимает строку, распознаваемые [CLSIDFromString](/windows/desktop/api/combaseapi/nf-combaseapi-clsidfromstring), с разделителями или без скобок.

Следующий пример приводит к возникновению ошибки C2778:

```
// C2778b.cpp
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778
```