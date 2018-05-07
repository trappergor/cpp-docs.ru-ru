---
title: Передача управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ee906061c7b51ade818b164c1d371a88ef3d462
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="transfers-of-control"></a>Передача управления
Можно использовать `goto` инструкции или **случай** метки в `switch` инструкцию, чтобы указать программу, которая обойдет инициализатор. Такой код не допускается, если объявление, содержащее инициализатор, не будет находиться в блоке, заключенном в блоке, в котором выполняется оператор jump.  
  
 В следующем примере показан цикл, в котором выполняется объявление и инициализация объектов `total`, `ch` и `i`. Также существует ошибочный оператор `goto`, который передает управление в обход инициализатора.  
  
```  
// transfers_of_control.cpp  
// compile with: /W1  
// Read input until a nonnumeric character is entered.  
int main()  
{  
   char MyArray[5] = {'2','2','a','c'};  
   int i = 0;  
   while( 1 )  
   {  
      int total = 0;  
  
      char ch = MyArray[i++];  
  
      if ( ch >= '0' && ch <= '9' )  
      {  
         goto Label1;  
  
         int i = ch - '0';  
      Label1:  
         total += i;   // C4700: transfers past initialization of i.  
      } // i would be destroyed here if  goto error were not present  
   else  
      // Break statement transfers control out of loop,  
      //  destroying total and ch.  
      break;  
   }  
}  
```  
  
 В предыдущем примере оператор `goto` пытается передать управление в обход инициализации `i`. Однако если бы объект `i` был объявлен, но не инициализирован, передача была бы допустима.  
  
 Объекты `total` и `ch`, объявленные в блоке, который служит в качестве *инструкции* из `while` инструкции, удаляются при выходе из этого блока с помощью `break` инструкции.  
  
