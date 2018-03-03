---
title: "Предупреждение компилятора C4687 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4687
dev_langs:
- C++
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41992e91b40fc17ef73ccb75828796b31ee3249e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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