---
title: "Ошибка компилятора C2390 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2390
dev_langs:
- C++
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8334477aef71e8f698bb70a48218c4b4b6c5ce0b
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2390"></a>Ошибка компилятора C2390
«Идентификатор»: класс неверного «спецификатор»  
  
 Класс хранения не является допустимым идентификатором глобальной области. Вместо недопустимого класса используется класс хранения по умолчанию.  
  
 Возможные решения:  
  
-   Если идентификатор является функцией, объявите его с `extern` хранилища.  
  
-   Если идентификатор является формальным параметром или локальной переменной, объявите его с автоматическим классом памяти.  
  
-   Если идентификатор является глобальной переменной, объявите его без класса памяти (автоматическая память).  
  
## <a name="example"></a>Пример  
  
-   Следующий пример приводит к возникновению ошибки C2390:  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```
