---
title: "Предупреждение компилятора C4687 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4687
dev_langs:
- C++
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
caps.latest.revision: 5
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f2dc847b6d75a563379b46e1375f93ceab9c7531
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4687"></a>Предупреждение компилятора C4687
«класс»: Запечатанный абстрактный класс не может реализовывать интерфейс «интерфейс»  
  
 Запечатанный абстрактный тип обычно только полезны для хранения статических функций-членов.  
  
 Дополнительные сведения см. в разделе [абстрактный](../../windows/abstract-cpp-component-extensions.md)и [запечатанные](../../windows/sealed-cpp-component-extensions.md).  
  
 По умолчанию C4687 выдается как ошибка. Можно подавить вывод предупреждения C4687 с [предупреждение](../../preprocessor/warning.md) pragma. Если вы уверены, что вы хотите реализовать интерфейс в запечатанном абстрактном типе, можно подавить вывод C4687.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4687.  
  
```  
// C4687.cpp  
// compile with: /clr /c  
interface class A {};  
  
ref struct B sealed abstract : A {};   // C4687  
ref struct C sealed : A {};   // OK  
ref struct D abstract : A {};   // OK  
```
