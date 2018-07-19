---
title: Ошибка компилятора C2872 | Документы Microsoft
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
ms.openlocfilehash: 636f263382c41806e04c50c0770340305a3013ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247156"
---
# <a name="compiler-error-c2872"></a>Ошибка компилятора C2872
"*символ*": неоднозначный символ  
  
Компилятор не может определить символ, который имеется в виду. Область — более чем один символ с указанным именем. См. заметки о следующие сообщение об ошибке для расположения файлов и объявления компилятор обнаружил для неоднозначный символ. Чтобы устранить эту проблему, можно полностью определить неоднозначный символ с помощью пространства имен, например, `std::byte` или `::byte`. Можно также использовать [псевдоним пространства имен](../../cpp/namespaces-cpp.md#namespace_aliases) для предоставления удобный для использования короткое имя включаемого пространства имен для устранения неоднозначности символы в исходном коде.  
  
C2872 может возникать, если файл заголовка [с помощью директивы](../../cpp/namespaces-cpp.md#using_directives), и включается в последующем файле заголовка, содержит тип, который также находится в пространстве имен, указанные в `using` директивы. Укажите `using` директив только после включения всех указанных файлов заголовка с `#include`.  
  
 Дополнительные сведения о C2872 статьях базы знаний [PRB: компилятора ошибок при использовании #import с XML в Visual C++ .NET](http://support.microsoft.com/kb/316317) и [«Ошибка C2872: «Платформа»: неоднозначный символ «сообщение об ошибке при использовании Пространство имен Windows::Foundation::Metadata в Visual Studio 2013](https://support.microsoft.com/kb/2890859).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2872, поскольку устанавливаются неоднозначная ссылка на переменную с именем `i`; две переменные с тем же именем:  
  
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