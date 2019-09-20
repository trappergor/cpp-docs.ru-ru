---
title: Ошибка компилятора C2778
ms.date: 11/04/2016
f1_keywords:
- C2778
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
ms.openlocfilehash: 98b5bf0a1315236f3ce96fd4b8c140ce1ab70a9f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501036"
---
# <a name="compiler-error-c2778"></a>Ошибка компилятора C2778

неверно сформированный GUID в __declspec (UUID ())

В расширенном атрибуте [UUID](../../cpp/uuid-cpp.md) указан неверный идентификатор GUID.

GUID должен быть строкой шестнадцатеричных чисел в следующем формате:

```
// C2778a.cpp
// compile with: /c
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};
```

Расширенный атрибут `uuid` принимает строки, распознаваемые [CLSIDFromString](/windows/win32/api/combaseapi/nf-combaseapi-clsidfromstring), с разделителями фигурных скобок или без них.

Следующий пример приводит к возникновению ошибки C2778:

```
// C2778b.cpp
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778
```