---
title: Ошибка компилятора C2872 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2872
dev_langs:
- C++
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 038c3475a6041dfb719bb2270a87ac2898f8b958
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036765"
---
# <a name="compiler-error-c2872"></a>Ошибка компилятора C2872

"*символ*": неоднозначный символ

Компилятор не может определить символ, который имеется в виду. Более чем один символ с указанным именем находится в области. См. примечания после сообщение об ошибке для расположения файлов и объявления компилятор обнаружил для неоднозначный символ. Чтобы устранить эту проблему, можно полностью определить неоднозначный символ с помощью его пространство имен, например, `std::byte` или `::byte`. Можно также использовать [псевдоним пространства имен](../../cpp/namespaces-cpp.md#namespace_aliases) предоставить удобный короткое имя для использования включенном пространстве имен, для устранения неоднозначности символов в исходном коде.

C2872 может возникать, если в файле заголовка [директива using](../../cpp/namespaces-cpp.md#using_directives), и включается в последующем файле заголовка, содержащий тип, который также находится в пространстве имен, заданном в `using` директива. Укажите `using` директив только после всех указанных файлов заголовка с `#include`.

Дополнительные сведения о C2872, см. в разделе статьи базы знаний [PRB: компилятора ошибки при использовании #import с XML в Visual C++ .NET](http://support.microsoft.com/kb/316317) и [«Ошибка C2872: «Платформа»: неоднозначный символ» сообщение об ошибке при использовании Пространство имен Windows::Foundation::Metadata в Visual Studio 2013](https://support.microsoft.com/kb/2890859).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2872, поскольку неоднозначных ссылок осуществляется переменной с именем `i`; две переменные с одинаковым именем:

```cpp
// C2872.cpp
// compile with: cl /EHsc C2872.cpp
namespace A {
   int i;
}

using namespace A;
int i;
int main() {
   ::i++;   // ok, uses i from global namespace
   A::i++;   // ok, uses i from namespace A
   i++;   // C2872 ambiguous: ::i or A::i?
   // To fix this issue, use the fully qualified name
   // for the intended variable.
}
```