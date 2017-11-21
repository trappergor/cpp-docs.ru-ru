---
title: "Ошибка компилятора C2466 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2466
dev_langs: C++
helpviewer_keywords: C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3c3ad19ce37aa51bd6b670da6e857d7eccce04ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2466"></a>Ошибка компилятора C2466
не удается выделить память для массива постоянного нулевого размера  
  
 Массив выделен или объявлен с нулевой размер. Константное выражение подсчета размера массива должно быть целое число больше нуля. Объявление массива с нулевым индексом допускается только для класса, структуры или члена объединения и только с расширениями Майкрософт ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 Следующий пример приводит к возникновению ошибки C2466:  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```