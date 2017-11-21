---
title: "Предупреждение (уровни 3 и 4) C4244 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4244
dev_langs: C++
helpviewer_keywords: C4244
ms.assetid: f116bb09-c479-4b4e-a647-fe629a1383f6
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bbcbe9d1c37827a28ce07849d909d58f5784a5a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-levels-3-and-4-c4244"></a>Предупреждение компилятора (уровни 3 и 4) C4244
conversion: преобразование из type1 в type2, возможна потеря данных  
  
 Целочисленный тип преобразуется в меньший целочисленный тип. Это предупреждение уровня 4, если *тип1* — `int` и *тип2* меньше, чем `int`. В противном случае — это уровень 3 (значение типа [__int64](../../cpp/int8-int16-int32-int64.md) переменной типа `unsigned int`). Возможна потеря данных.  
  
 При возникновении ошибки C4244 следует изменить программу так, чтобы использовались совместимые типы, или добавить в код логику, чтобы диапазон возможных значений всегда был совместим с типами, которые вы используете.  
  
 Предупреждение C4244 также может возникнуть на уровне 2. в разделе [Предупреждение компилятора (уровень 2) C4244](../../error-messages/compiler-warnings/compiler-warning-level-2-c4244.md) для получения дополнительной информации.  
  
 Это преобразование может вызвать проблемы из-за неявных преобразований.  
  
 Следующий пример приводит к возникновению ошибки C4244.  
  
```  
// C4244_level4.cpp  
// compile with: /W4  
int aa;  
unsigned short bb;  
int main() {  
   int b = 0, c = 0;  
   short a = b + c;   // C4244  
  
   bb += c;   // C4244  
   bb = bb + c;   // C4244  
   bb += (unsigned short)aa;   // C4244  
   bb = bb + (unsigned short)aa;   // OK  
}  
```  
  
 Дополнительные сведения см. в разделе [обычные арифметические преобразования](../../c-language/usual-arithmetic-conversions.md).  
  
```  
// C4244_level3.cpp  
// compile with: /W3  
int main() {  
   __int64 i = 8;  
   unsigned int ii = i;   // C4244  
}  
```  
  
 Предупреждение C4244 может возникнуть при создании кода для 64-разрядных сред, который не вызывает предупреждение при построении для 32-разрядных сред. Например, указатели 32-разрядных платформах представлены 32-разрядными значениям, а на 64-разрядных платформах — 64-разрядными.  
  
 Следующий пример приводит к возникновению ошибки C4244 при компиляции для 64-разрядных сред:  
  
```  
// C4244_level3_b.cpp  
// compile with: /W3   
int main() {  
   char* p1 = 0;  
   char* p2 = 0;  
   int x = p2 - p1;   // C4244  
}  
```