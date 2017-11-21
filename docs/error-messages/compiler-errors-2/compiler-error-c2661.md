---
title: "Ошибка компилятора C2661 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2661
dev_langs: C++
helpviewer_keywords: C2661
ms.assetid: 60021467-71cd-451b-9877-23840c69309f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dc5d33bbb0dd1053a200791952848146450e9a16
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2661"></a>Ошибка компилятора C2661
«функция»: нет перегруженной функции принимает номер параметра  
  
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