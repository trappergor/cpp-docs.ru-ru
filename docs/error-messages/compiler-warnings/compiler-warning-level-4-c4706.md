---
title: Предупреждение (уровень 4) C4706 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4706
dev_langs:
- C++
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1131147a9600525746cb3e89119189ed9e5026a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4706"></a>Предупреждение компилятора (уровень 4) C4706
Назначение в пределах условного выражения  
  
 Тестовое значение в условном выражении создана в результате назначения.  
  
 Назначения имеет значение (значение в левой части назначения), которое может использоваться в другом, включая выражение проверки законом.  
  
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
  
 Предупреждение может возникнуть, даже если дважды скобки вокруг условие теста:  
  
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
  
 Если нужно проверить связь и не делать назначения, использовать `==` оператор. Например, в следующей строке проверяется, является ли и b равны:  
  
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
  
 Если вы собираетесь значения результат присваивания, проверьте, убедитесь, что назначение не нулевой или not null. Например следующий код не создаст это предупреждение:  
  
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