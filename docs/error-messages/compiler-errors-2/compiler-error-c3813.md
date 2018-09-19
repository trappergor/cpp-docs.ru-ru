---
title: Ошибка компилятора C3813 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3813
dev_langs:
- C++
helpviewer_keywords:
- C3813
ms.assetid: ffdbc489-71bf-4cd6-988c-f824c9ab3ceb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b8984feb5b657c26d2137eb9a3c648f1bcf442bf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066275"
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