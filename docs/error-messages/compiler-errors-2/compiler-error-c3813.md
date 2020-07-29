---
title: Ошибка компилятора C3813
ms.date: 11/04/2016
f1_keywords:
- C3813
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
ms.openlocfilehash: 88aca16363af22a6671832264889b1a26e43d460
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223373"
---
# <a name="compiler-error-c3813"></a>Ошибка компилятора C3813

объявление свойства должно находиться только в пределах определения управляемого типа или типа WinRT

[Свойство](../../dotnet/how-to-use-properties-in-cpp-cli.md) может быть объявлено только в управляемом или среда выполнения Windows типе. Собственные типы не поддерживают **`property`** ключевое слово.

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C3813 и приводятся сведения по ее устранению.

```cpp
// C3813.cpp
// compile by using: cl /c /clr C3813.cpp
class A
{
   property int Int; // C3813
};

ref class B
{
   property int Int; // OK - declared within managed type
};
```
