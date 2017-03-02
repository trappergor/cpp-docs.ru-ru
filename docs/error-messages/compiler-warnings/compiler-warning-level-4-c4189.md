---
title: "Компилятор C4189 предупреждение (уровень 4) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4189
dev_langs:
- C++
helpviewer_keywords:
- C4189
ms.assetid: 7ad9242c-228e-4054-8244-5e914b618ef3
caps.latest.revision: 6
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: aa0f1f0520bb5edacf6df4d5a7971b274dad0c21
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4189"></a>Предупреждение компилятора (уровень 4) C4189
"идентификатор": локальная переменная инициализирована, но не использована  
  
 Переменная объявлена и инициализирована, но не используется.  
  
 Следующий пример приводит к возникновению предупреждения C4189:  
  
```  
// C4189.cpp  
// compile with: /W4  
int main() {  
   int a = 1;   // C4189, remove declaration to resolve  
}  
```
