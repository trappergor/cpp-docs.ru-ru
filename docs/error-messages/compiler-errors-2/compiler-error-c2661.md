---
title: "Ошибка компилятора C2661 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2661
dev_langs:
- C++
helpviewer_keywords:
- C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c0d9d871feb7a673d0937ea65942c7a9733b4261
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2661"></a>Ошибка компилятора C2661
«функция»: нет перегруженной функции, принимающей числовые параметры  
  
 Возможные причины:  
  
1.  Неверные фактические параметры в вызове функции.  
  
2.  Отсутствует объявление функции.  
  
 Следующий пример приводит к возникновению ошибки C2661:  
  
```  
// C2661.cpp  
void func( int ){}  
void func( int, int ){}  
int main() {  
   func( );   // C2661 func( void ) was not declared  
   func( 1 );   // OK func( int ) was declared  
}  
```
