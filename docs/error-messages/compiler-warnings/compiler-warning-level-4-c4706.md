---
title: "Предупреждение (уровень 4) C4706 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4706
dev_langs:
- C++
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
caps.latest.revision: 6
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
ms.openlocfilehash: d4f4edcbf4a4cb147c2acb8e6cb530a4a0f9a9a9
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-4-c4706"></a>Предупреждение компилятора (уровень 4) C4706
назначение в пределах условного выражения  
  
 Тестовое значение в условном выражении создана в результате присваивания.  
  
 Назначение имеет значение (значение левой части назначения), которое может использоваться в другом, включая тестовое выражение законом.  
  
 Следующий пример приводит к возникновению ошибки C4706:  
  
```  
// C4706a.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a  = b ) // C4706  
   {  
   }  
}  
```  
  
 Предупреждение будет происходить, даже если двойные скобки вокруг условия теста.  
  
```  
// C4706b.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a  =  b ) ) // C4706  
   {  
   }  
}  
```  
  
 Если нужно проверить связь и не делать назначения, использовать `==` оператор. Например, в следующей строке проверяется, является ли и b равно:  
  
```  
// C4706c.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a == b )  
   {  
   }  
}  
```  
  
 Если вы собираетесь выполнить значения назначения, проверьте, убедитесь, что назначение не нулевой или not null. Например следующий код не создаст это предупреждение:  
  
```  
// C4706d.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a = b ) != 0 )  
   {  
   }  
}  
```
