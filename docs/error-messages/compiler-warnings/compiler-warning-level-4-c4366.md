---
title: "Предупреждение (уровень 4) C4366 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4366
dev_langs: C++
helpviewer_keywords: C4366
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d610bfcf2e432870fc081298d3dfc3a60c73bd4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4366"></a>Предупреждение компилятора (уровень 4) C4366
Результатом унарного оператора «оператор» может быть невыровненным  
  
 Если член структуры не выровнен вследствие упаковки, компилятор выдает предупреждение, когда этот адрес участника назначается для выровненного указателя. По умолчанию все указатели являются выровненными.  
  
 Чтобы устранить предупреждение C4366, изменении выравнивания структуры или объявить указатель с [__unaligned](../../cpp/unaligned.md) ключевое слово.  
  
 Дополнительные сведения см. в разделе __unaligned и [пакет](../../preprocessor/pack.md).  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4366.  
  
```  
// C4366.cpp  
// compile with: /W4 /c  
// processor: IPF x64  
#pragma pack(1)  
struct X {  
   short s1;  
   int s2;  
};  
  
int main() {  
   X x;  
   short * ps1 = &x.s1;   // OK  
   int * ps2 = &x.s2;   // C4366  
}  
```