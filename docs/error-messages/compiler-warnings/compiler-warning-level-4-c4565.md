---
title: Предупреждение компилятора (уровень 4) C4565
ms.date: 08/27/2018
f1_keywords:
- C4565
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
ms.openlocfilehash: 5eccb3c29da612a39f7fcdf4ef25dedb898c8d43
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198332"
---
# <a name="compiler-warning-level-4-c4565"></a>Предупреждение компилятора (уровень 4) C4565

> "*функция*": переопределение; символ был ранее объявлен с помощью __declspec (*Модификатор*)

## <a name="remarks"></a>Remarks

Символ был переопределен или объявлен повторно, а второе определение или объявление, в отличие от первого определения или объявления, не имеет модификатора `__declspec` (*Модификатор*). Это предупреждение носит информационный характер. Чтобы устранить это предупреждение, удалите одно из определений.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4565:

```cpp
// C4565.cpp
// compile with: /W4 /LD
__declspec(noalias) void f();
void f();   // C4565
```
