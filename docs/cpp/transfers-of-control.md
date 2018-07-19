---
title: Передача управления | Документация Майкрософт
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
ms.openlocfilehash: 8bec66d25be2cb56c75f42f60af2ccd5e3f759ad
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944796"
---
# <a name="transfers-of-control"></a>Передача управления
Можно использовать **goto** инструкции или **случай** метки в **переключения** инструкцию, чтобы указать программу, которая обойдет инициализатор. Такой код не допускается, если объявление, содержащее инициализатор, не будет находиться в блоке, заключенном в блоке, в котором выполняется оператор jump.  
  
 В следующем примере показан цикл, в котором выполняется объявление и инициализация объектов `total`, `ch` и `i`. Имеется также ошибочный **goto** инструкцию, которая передает управление в обход инициализатора.  
  
```cpp 
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
  
 В приведенном выше примере **goto** оператор пытается передать управление в обход инициализации `i`. Однако если бы объект `i` был объявлен, но не инициализирован, передача была бы допустима.  
  
 Объекты `total` и `ch`, объявленные в блоке, который служит в качестве *инструкции* из **хотя** инструкции, удаляются при выходе из этого блока с помощью  **break** инструкции.  
  
