---
title: "Значение категории: Значения lvalue и rvalue (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- R-values [C++]
- L-values [C++]
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 34513ba6799b1f70d16867571d38185420fa3576
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="lvalues-and-rvalues-visual-c"></a>Значения lvalue и rvalue (Visual C++)
Каждое выражение C++, имеет тип, а также принадлежит *категории значение*. Значение категории являются основой для правила, в которых компиляторы должны следовать при создание, копирование и перемещение временные объекты во время вычисления выражения. 

 Стандарт C ++ 17 категорий значение выражения определяет следующим образом:

- Объект *glvalue* — это выражение, вычисление которого определяет удостоверение объекта, битового поля или функции. 
- Объект *prvalue* выражение, вычисление которого инициализирует битового поля или объекта, или вычисляет значение операнда оператора, как указано в контексте, в котором он отображается. 
- *Xvalue* является glvalue, указывающую объекта или битового поля, ресурсы которого может быть повторно использован (обычно, поскольку он находится в конце времени его существования). [Пример: определенных видов выражений, содержащих ссылки rvalue (8.3.2) yield xvalues, такие как вызов функции, тип возвращаемого значения является ссылкой rvalue или приведение к типу ссылки rvalue. ] 
- *Lvalue* является glvalue, который не является xvalue. 
- *Rvalue* prvalue или xvalue. 

На следующей схеме показана связи между категории:

 ![Категории значение выражения C++](media/value_categories.png "категорий значение выражения в C++")  
 
 Значение lvalue есть адрес, который можно получить доступ к программе. Примеры выражений lvalue включают имена переменных, включая `const` переменных, элементов массива, функция вызовов, которые возвращают ссылки lvalue, битовые поля, объединения и членов класса. 
 
 Выражение prvalue не имеет адреса, доступном в программе. Примеры выражений prvalue включают литералы, вызовы функций, возвращающих тип не является ссылкой и временные объекты, созданные во время вычислений выражения, но доступны только компилятором. 

 Выражение xvalue не имеет адреса, но может использоваться для инициализации ссылка rvalue, которое предоставляет доступ к выражению. Примеры вызовов функций, возвращающих ссылка rvalue и индекс массива, член и указателя выражения элементов, где массива или объекта является ссылкой rvalue. 
 
 В следующем примере показано несколько правильных и неправильных способов использования значений lvalue и rvalues.  
  
```  
// lvalues_and_rvalues2.cpp  
int main()  
{  
   int i, j, *p;  
  
   // Correct usage: the variable i is an lvalue and the literal 7 is a prvalue.  
   i = 7;  
  
   // Incorrect usage: The left operand must be an lvalue (C2106).  `j * 4` is a prvalue.
   7 = i; // C2106  
   j * 4 = 7; // C2106  
  
   // Correct usage: the dereferenced pointer is an lvalue.  
   *p = i;   
  
   const int ci = 7;  
   // Incorrect usage: the variable is a non-modifiable lvalue (C3892).  
   ci = 9; // C3892  
  
   // Correct usage: the conditional operator returns an lvalue.  
   ((i < 3) ? i : j) = 7;  
}  
```  
  
> [!NOTE]
>  В примерах этого раздела показано правильное и неправильное использование при неперегруженных операторах. Перегрузив операторы, можно преобразовать выражение, такое как `j * 4`, в значение lvalue.  

  
 Условия *lvalue* и *rvalue* часто используются при ссылке на ссылки на объект. Дополнительные сведения о ссылках см. в разделе [декларатор ссылки Lvalue: &](../cpp/lvalue-reference-declarator-amp.md) и [декларатор ссылки Rvalue: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../cpp/basic-concepts-cpp.md)   
 [Декларатор ссылки lvalue: &](../cpp/lvalue-reference-declarator-amp.md)   
 [Декларатор ссылки Rvalue: &&](../cpp/rvalue-reference-declarator-amp-amp.md)