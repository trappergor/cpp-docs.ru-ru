---
title: "Рекурсивные функции | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 38d98e568b88d8b26be2a04a9b643fb0d99a9712
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="recursive-functions"></a>Рекурсивные функции
Любая функция в программе на языке C может вызываться рекурсивно, т. е. может вызывать сама себя. Число рекурсивных вызовов ограничено размером стека. Сведения о параметрах компоновщика, определяющих размер стека, см. в описании параметра компоновщика [/STACK (Stack Allocations)](../build/reference/stack-stack-allocations.md) (/STACK — Распределение стека). При каждом вызове функции для параметров и переменных **auto** и **register** выделяется новая память, чтобы не перезаписывались их значения в предыдущих (незаконченных) вызовах. Параметры доступны непосредственно только экземпляру функции, в котором они были созданы. Последующим экземплярам функции предыдущие параметры непосредственно недоступны.  
  
 Обратите внимание, что для переменных, объявленных с описателем **static**, новая память при новом рекурсивном вызове не требуется. Их память существует в течение времени жизни программы. При каждой ссылке на такую переменную осуществляется доступ к той же области памяти.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируются рекурсивные вызовы.  
  
```  
int factorial( int num );      /* Function prototype */  
  
int main()  
{  
    int result, number;  
    .  
    .  
    .  
    result = factorial( number );  
}  
  
int factorial( int num )      /* Function definition */  
{  
    .  
    .  
    .  
    if ( ( num > 0 ) || ( num <= 10 ) )  
        return( num * factorial( num - 1 ) );  
}  
  
```  
  
## <a name="see-also"></a>См. также  
 [Вызовы функций](../c-language/function-calls.md)
