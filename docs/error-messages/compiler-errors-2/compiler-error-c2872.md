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
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: d53dbd9429ba3c1a525b85a3ef9f2e70152ddfa2
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2872"></a>Ошибка компилятора C2872
«символ»: неоднозначный символ  
  
Компилятор не может определить символ, который имеется в виду.  
  
C2872 может возникать, если файл заголовка [с помощью директивы](../../cpp/namespaces-cpp.md#using_directives)и в последующем файле заголовка включено и он содержит тип, который также находится в пространстве имен, заданном в `using` директивы. Укажите `using` только после включения всех необходимых файлов указываются с помощью директивы `#include`.  
  
 Дополнительные сведения о C2872 статьях базы знаний [PRB: компилятора ошибок при использовании #import с XML в Visual C++ .NET](http://support.microsoft.com/kb/316317) и [«Ошибка C2872: «Платформа»: неоднозначный символ «сообщение об ошибке при использовании Windows::Foundation::Metadata имен в Visual Studio 2013](https://support.microsoft.com/kb/2890859).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2872:  
  
```cpp  
// C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok  
   A::i++;   // ok  
   i++;   // C2872 ::i or A::i?  
}  
```
