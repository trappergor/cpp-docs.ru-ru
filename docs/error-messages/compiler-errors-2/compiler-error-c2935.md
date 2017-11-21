---
title: "Ошибка компилятора C2935 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2935
dev_langs: C++
helpviewer_keywords: C2935
ms.assetid: e11ef90d-0756-4e43-8a09-4974c6aa72a3
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d270ed23d9bddc9ef14d1ebd9a6aca78f24d59f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2935"></a>Ошибка компилятора C2935
"класс": идентификатор класса типа переопределен как глобальная функция  
  
 Универсальный класс или класс-шаблон нельзя использовать в качестве глобальной функции.  
  
 Эта ошибка может возникнуть при неправильной расстановке скобок.  
  
 Следующий пример приводит к возникновению ошибки C2935:  
  
```  
// C2935.cpp  
// compile with: /c  
template<class T>  
struct TC {};   
void TC<int>() {}   // C2935  
  
// OK  
struct TC2 {};   
void TC2() {}  
```  
  
 Ошибка C2935 также может возникнуть при использовании универсальных шаблонов:  
  
```  
// C2935b.cpp  
// compile with: /clr /c  
generic<class T>   
ref struct GC { };  
void GC<int>() {}   // C2935  
void GC() {}   // OK  
```