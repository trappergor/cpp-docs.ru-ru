---
title: Предупреждение (уровень 1) C4042 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4042
dev_langs:
- C++
helpviewer_keywords:
- C4042
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bcc4123c18eb9765841a5f6b54446cd064407700
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278389"
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