---
title: Предупреждение компилятора C4394
ms.date: 11/04/2016
f1_keywords:
- C4394
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
ms.openlocfilehash: ad6b9624a1bf510465843167d104d1bec189bc70
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87197362"
---
# <a name="compiler-warning-c4394"></a>Предупреждение компилятора C4394

"функция": символ в домене приложения не должен помечаться __declspec (dllexport)

Функция, помеченная [appdomain](../../cpp/appdomain.md) **`__declspec`** модификатором AppDomain, компилируется в MSIL (не в машинный код), а экспорт таблиц (модификатор[экспорта](../../windows/export.md) **`__declspec`** ) не поддерживается для управляемых функций.

Можно объявить управляемую функцию, чтобы иметь открытый доступ. Дополнительные сведения см. в разделе [видимость типов](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) и [видимость элементов](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).

C4394 всегда выдается как ошибка.  Это предупреждение можно отключить с помощью `#pragma warning` или **/WD**; см. [предупреждение](../../preprocessor/warning.md) или [/W,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/Wall,/WD,/We,/WO,/WV,/WX (уровень предупреждений)](../../build/reference/compiler-option-warning-level.md) для получения дополнительных сведений.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4394.

```cpp
// C4394.cpp
// compile with: /clr /c
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394
__declspec(dllexport) int g2 = 0;   // OK
```
