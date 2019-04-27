---
title: Предупреждение компилятора (уровень 4) C4565
ms.date: 08/27/2018
f1_keywords:
- C4565
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
ms.openlocfilehash: b655dcfb456d32e45833e89e5a48926ad70d1d9e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62220485"
---
# <a name="compiler-warning-level-4-c4565"></a>Предупреждение компилятора (уровень 4) C4565

> "*функция*": переопределение; символ был объявлен ранее при помощи __declspec (*модификатор*)

## <a name="remarks"></a>Примечания

Символ был или определении и второе определение или объявление, в отличие от первого определения или объявления, не имели `__declspec` модификатор (*модификатор*). Это предупреждение носит информационный характер. Чтобы устранить это предупреждение, удалите одно из определений.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4565:

```cpp
// C4565.cpp
// compile with: /W4 /LD
__declspec(noalias) void f();
void f();   // C4565
```