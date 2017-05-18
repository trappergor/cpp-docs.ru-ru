---
title: "Компилятора (уровни 3 и 4) предупреждение C4244 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4244
dev_langs:
- C++
helpviewer_keywords:
- C4244
ms.assetid: f116bb09-c479-4b4e-a647-fe629a1383f6
caps.latest.revision: 16
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
ms.openlocfilehash: ffc1f0012d7b65ab959503c3845b1f7a04268676
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-levels-3-and-4-c4244"></a>Предупреждение компилятора (уровни 3 и 4) C4244
conversion: преобразование из type1 в type2, возможна потеря данных  
  
 Целочисленный тип преобразуется в меньший целочисленный тип. Если это предупреждение уровня&4; *type1* — `int` и *type2* меньше, чем `int`. В противном случае — это уровень 3 (присвоено значение типа [__int64](../../cpp/int8-int16-int32-int64.md) переменной типа `unsigned int`). Возможна потеря данных.  
  
 При возникновении ошибки C4244 следует изменить программу так, чтобы использовались совместимые типы, или добавить в код логику, чтобы диапазон возможных значений всегда был совместим с типами, которые вы используете.  
  
 Предупреждение C4244 может появиться и на уровне 2. в разделе [Предупреждение компилятора (уровень 2) C4244](../../error-messages/compiler-warnings/compiler-warning-level-2-c4244.md) подробнее.  
  
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
