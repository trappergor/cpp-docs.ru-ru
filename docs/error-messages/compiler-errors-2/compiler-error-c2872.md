---
title: "Ошибка компилятора C2872 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2872
dev_langs:
- C++
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: c81fc315c4bb893b96876b7b67b42806a3246583
ms.lasthandoff: 04/29/2017

---
# <a name="compiler-error-c2872"></a>Ошибка компилятора C2872
"*символ*": неоднозначный символ  
  
Компилятор не может определить символ, который имеется в виду. Область — более чем один символ с указанным именем. См. заметки о следующие сообщение об ошибке для расположения файлов и объявления компилятор обнаружил для неоднозначный символ. Чтобы устранить эту проблему, можно полностью определить неоднозначный символ с помощью пространства имен, например, `std::byte` или `::byte`. Можно также использовать [псевдоним пространства имен](../../cpp/namespaces-cpp.md#namespace_aliases) для предоставления удобный для использования короткое имя включаемого пространства имен для устранения неоднозначности символы в исходном коде.  
  
C2872 может возникать, если файл заголовка [с помощью директивы](../../cpp/namespaces-cpp.md#using_directives), и включается в последующем файле заголовка, содержит тип, который также находится в пространстве имен, указанные в `using` директивы. Укажите `using` директив только после включения всех указанных файлов заголовка с `#include`.  
  
 Дополнительные сведения о C2872 статьях базы знаний [PRB: компилятора ошибок при использовании #import с XML в Visual C++ .NET](http://support.microsoft.com/kb/316317) и [«Ошибка C2872: «Платформа»: неоднозначный символ «сообщение об ошибке при использовании Windows::Foundation::Metadata имен в Visual Studio 2013](https://support.microsoft.com/kb/2890859).  
  
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
