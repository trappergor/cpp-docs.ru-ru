---
title: "Рекурсивные функции | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- functions [C], recursive
- function calls, recursive
- functions [C], calling recursively
- recursive function calls
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcbe38eb67a31f6bb62750b44df57aa9d64b9272
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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