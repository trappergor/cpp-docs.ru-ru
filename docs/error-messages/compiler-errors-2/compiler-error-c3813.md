---
title: Ошибка компилятора C3813
ms.date: 11/04/2016
f1_keywords:
- C3813
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
ms.openlocfilehash: c16ce501e25040a7ac7672a9ea131b4fe89570f5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165617"
---
# <a name="compiler-error-c3813"></a>Ошибка компилятора C3813

объявление свойства должно находиться только в пределах определения управляемого типа или типа WinRT

[Свойство](../../dotnet/how-to-use-properties-in-cpp-cli.md) может быть объявлено только в управляемом или среда выполнения Windows типе. Собственные типы не поддерживают ключевое слово `property`.

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
