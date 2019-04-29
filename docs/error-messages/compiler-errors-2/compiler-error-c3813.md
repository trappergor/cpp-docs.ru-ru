---
title: Ошибка компилятора C3813
ms.date: 11/04/2016
f1_keywords:
- C3813
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
ms.openlocfilehash: 302b21d709424cda50abd0247f7b82048511cd73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384313"
---
# <a name="compiler-error-c3813"></a>Ошибка компилятора C3813

объявление свойства должно находиться только в пределах определения управляемого типа или типа WinRT

Объект [свойство](../../dotnet/how-to-use-properties-in-cpp-cli.md) могут объявляться только в пределах управляемого или среды выполнения Windows тип. Собственные типы не поддерживают ключевое слово `property`.

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