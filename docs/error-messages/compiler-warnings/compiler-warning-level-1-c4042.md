---
title: "Предупреждение (уровень 1) C4042 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4042
dev_langs: C++
helpviewer_keywords: C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3369b2786c552e408e8eedf8e6ed8bf73f272ff6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4042"></a>Предупреждение (уровень 1) C4042 компилятора
«Идентификатор»: имеет недопустимый класс хранения  
  
 Заданный класс хранения не может использоваться с этим идентификатором в данном контексте. Компилятор использует класс хранения по умолчанию вместо:  
  
-   `extern`, если *идентификатор* является функцией.  
  
-   **Auto**, если *идентификатор* формального параметра или локальной переменной.  
  
-   Класс места для хранения, если *идентификатор* является глобальной переменной.  
  
 Это предупреждение может быть вызвано задан класс хранения отличный от **зарегистрировать** в объявлении параметра.  
  
 Следующий пример приводит к возникновению ошибки C4042  
  
```  
// C4042.cpp  
// compile with: /W1 /LD  
int func2( __declspec( thread ) int tls_i )    // C4042  
// try the following line instead  
// int func2( int tls_i )  
{  
   return tls_i;  
}  
```