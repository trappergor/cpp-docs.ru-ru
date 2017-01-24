---
title: "Глобальные константы в C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "константы, общие"
  - "глобальные константы"
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Глобальные константы в C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Глобальные константы C\+\+ имеют статическую связь.  В этом отличие от С.  При попытке использования глобальных констант в C\+\+ в нескольких файлах может возникнуть неразрешенная внешняя ошибка.  Компилятор оптимизирует глобальные константы, не оставляя места для переменных.  
  
 Одним из способов устранения ошибки является включение инициализации констант в файл заголовка и включение заголовка в файл CPP, когда необходимо, как если бы это был прототип функции.  Другой способ — это сделать переменной "не\-константой" и использовать ссылку на константу при ее вычислении.  
  
 Следующий пример приводит к возникновению ошибки C2019:  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 И далее,  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## См. также  
 [Ошибка средств компоновщика LNK2019](../Topic/Linker%20Tools%20Error%20LNK2019.md)