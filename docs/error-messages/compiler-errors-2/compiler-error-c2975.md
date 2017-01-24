---
title: "Ошибка компилятора C2975 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2975"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2975"
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2975
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"arg": недопустимый аргумент шаблона для "типа", требуется константное выражение времени компиляции  
  
 Аргумент шаблона не соответствует объявлению шаблона; константное выражение должно заключаться в угловые скобки.  Не разрешается использование переменных в качестве фактического аргумента шаблона.  Следует проверить определение шаблона, чтобы найти правильные типы.  
  
 Следующий пример приводит к возникновению ошибки C2975:  
  
```  
// C2975.cpp  
template<int I>  
class X {};  
  
int main() {  
   int i = 4, j = 2;  
   X<i + j> x1;   // C2975  
   X<6> x2;   // OK  
}  
```  
  
 Ошибка C2975 также может возникнуть при использовании директивы \_\_LINE\_\_ в качестве константного выражения времени компиляции с параметром [\/ZI](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md).  Одним из способов устранения проблемы является компиляция с параметром [\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) вместо параметра **\/ZI**.  
  
```  
// C2975b.cpp  
// compile with: /ZI  
// processor: x86  
template<long line>   
void test(void) {}  
  
int main() {  
   test<__LINE__>();   // C2975  
}  
```