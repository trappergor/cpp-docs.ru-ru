---
title: "Ошибка компилятора C3455 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3455
dev_langs:
- C++
helpviewer_keywords:
- C3455
ms.assetid: 218e5cfe-5391-4eeb-81c2-85c47e3a6cd2
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: f81e55a33eaeccafab5809eb70337b15044cbd03
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3455"></a>Ошибка компилятора C3455
"атрибут": ни один из конструкторов атрибута не соответствует аргументам  
  
 Недопустимое значение использовалось для объявления атрибута.  В разделе [атрибут](../../windows/attribute.md) для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3455:  
  
```  
// C3455.cpp  
// compile with: /clr /c  
using namespace System;  
  
[attribute("MyAt")]   // C3455  
// try the following line instead  
// [attribute(All)]  
ref struct MyAttr {  
   MyAttr() {}  
};  
```
