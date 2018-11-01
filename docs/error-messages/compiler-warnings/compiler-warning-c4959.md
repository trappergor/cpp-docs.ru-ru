---
title: Предупреждение компилятора C4959
ms.date: 11/04/2016
f1_keywords:
- C4959
helpviewer_keywords:
- C4959
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
ms.openlocfilehash: 646347dec7bc2bac7fa73c8f754d2f9549cb2ba6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473662"
---
# <a name="compiler-warning-c4959"></a>Предупреждение компилятора C4959

> не удается определить неуправляемую структуру "*тип*" в/CLR: safe, поскольку доступ к ее членам выдает код, недоступный для проверки

## <a name="remarks"></a>Примечания

Обращение к члену неуправляемого типа приводит к формированию непроверяемого (peverify.exe) образа.

Дополнительные сведения см. в разделе [чистый и проверяемый код (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/CLR: safe** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017.

Это предупреждение выдается в качестве ошибки, и его можно отключить с помощью прагмы [warning](../../preprocessor/warning.md) или параметра компилятора [/wd](../../build/reference/compiler-option-warning-level.md) .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению предупреждения C4959:

```cpp
// C4959.cpp
// compile with: /clr:safe

// Uncomment the following line to resolve.
// #pragma warning( disable : 4959 )
struct X {
   int data;
};

int main() {
   X x;
   x.data = 10;   // C4959
}
```