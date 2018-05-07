---
title: Предупреждение компилятора C4687 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4687
dev_langs:
- C++
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ad45c4bb2456b3bc23114233c084bbad1551e27
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-c4687"></a>Предупреждение компилятора C4687
«класс»: Запечатанный абстрактный класс не может реализовывать интерфейс «интерфейс»  
  
 Запечатанный абстрактный тип полезен обычно только для хранения статических функций-членов.  
  
 Дополнительные сведения см. в разделе [абстрактный](../../windows/abstract-cpp-component-extensions.md)и [запечатанный](../../windows/sealed-cpp-component-extensions.md).  
  
 C4687 выдается как ошибка, по умолчанию. Можно подавить вывод предупреждения C4687 с [предупреждение](../../preprocessor/warning.md) pragma. Если вы уверены, что нужно реализовать интерфейс в Запечатанный абстрактный тип, можно подавить вывод C4687.  
  
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