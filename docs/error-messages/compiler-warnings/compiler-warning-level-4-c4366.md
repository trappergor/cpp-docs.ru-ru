---
title: "Предупреждение компилятора (уровень 4) C4366 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4366"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4366"
ms.assetid: 65d2942f-3741-42f4-adf2-4920d5a055ca
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Предупреждение компилятора (уровень 4) C4366
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Результат применения унарного оператора "оператор" может быть невыровненным  
  
 Если член структуры не выровнен вследствие упаковки, компилятор выводит предупреждение при назначении адреса данного члена для выровненного указателя.  По умолчанию все указатели являются выровненными.  
  
 Чтобы устранить предупреждение C4366, следует либо изменить выравнивание структуры, либо объявить указатель с ключевым словом [\_\_unaligned](../../cpp/unaligned.md).  
  
 Дополнительные сведения см. в описании директив  \_\_unaligned и [pack](../../preprocessor/pack.md).  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки C4366.  
  
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