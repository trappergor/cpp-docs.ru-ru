---
title: "C2429 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2429
dev_langs:
- C++
helpviewer_keywords:
- C2429
ms.assetid: 57ff6df9-5cf1-49f3-8bd8-4e550dfd65a0
caps.latest.revision: 9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: eb0c1bf407d1478451c246cf615d031ef6c45bf9
ms.openlocfilehash: 7d2c27ccdba28720596984c46c9d24f9d29c7b15
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2429"></a>C2429 ошибки компилятора
"*функция языка*«требует флаг компилятора»*параметр компилятора*"  
  
Функции языка требует параметр компилятора, определенные для поддержки.  
  
Ошибка C2429: функцией языка «вложенные пространства имен-» определение требует флаг компилятора "/ std:c ++ последнюю" генерируется при попытке определить *составных имен*, пространство имен, содержащее одно или несколько имен вложенной области видимости пространства имен, начиная с Visual Studio 2015 г. обновление 3. Составное пространство имен определения, не разрешены в C++ до C ++&17;. Компилятор поддерживает составное пространство имен определения при [/std:c ++ последнюю](../../build/reference/std-specify-language-standard-version.md) указан параметр компилятора:  
```cpp  
// C2429a.cpp  
namespace a::b { int i; } // C2429 starting in Visual C++ 2015 Update 3.  
                          // Use /std:c++latest to fix, or do this:  
// namespace a { namespace b { int i; }}  
  
int main() {  
   a::b::i = 2;  
}  
```  
