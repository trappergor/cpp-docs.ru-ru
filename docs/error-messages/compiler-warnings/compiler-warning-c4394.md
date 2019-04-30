---
title: Предупреждение компилятора C4394
ms.date: 11/04/2016
f1_keywords:
- C4394
helpviewer_keywords:
- C4394
ms.assetid: 5de94de0-17e3-4e7c-92f4-5c3c1b825120
ms.openlocfilehash: 00c9e139e920473590389c05f076a7cd91a4fb8d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311482"
---
# <a name="compiler-warning-c4394"></a>Предупреждение компилятора C4394

«функция»: символ по доменам приложения не следует помечать с помощью __declspec(dllexport)

Функция, помеченная [appdomain](../../cpp/appdomain.md) `__declspec` модификатор компилируется в код MSIL (не в машинный код) и экспорт таблицы ([Экспорт](../../windows/export.md) `__declspec` модификатор) не поддерживаются для управляемых функций.

Можно объявить управляемой функции иметь доступность уровня public. Дополнительные сведения см. в разделе [введите видимость](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) и [видимость членов](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility).

C4394 всегда выдается как ошибка.  Вы можете отключить это предупреждение с помощью `#pragma warning` или **/wd**; см. в разделе [предупреждение](../../preprocessor/warning.md) или [/w, / W0, / W1, / w2, / w3, / W4, / W1, / w2, / w3, / W4, / Wall, / WD, / we, / WO, / wv, /WX (уровень предупреждений)](../../build/reference/compiler-option-warning-level.md)Дополнительные сведения.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4394.

```
// C4394.cpp
// compile with: /clr /c
__declspec(dllexport) __declspec(appdomain) int g1 = 0;   // C4394
__declspec(dllexport) int g2 = 0;   // OK
```