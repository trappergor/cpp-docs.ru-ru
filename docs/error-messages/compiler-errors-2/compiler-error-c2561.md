---
title: "Ошибка компилятора C2561 | Microsoft Docs"
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
  - "C2561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2561"
ms.assetid: 0abe955b-53a6-4a3c-8362-b1a8eb40e8d1
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор" : функция должна возвращать значение  
  
 Функция была объявлена как возвращающая значение, но ее определение не содержит оператора `return`.  
  
 Эта ошибка может быть вызвана неверным прототипом функции.  
  
1.  Если функция не возвращает значение, используйте [void](../../cpp/void-cpp.md) в качестве типа возвращаемого значения.  
  
2.  Проверьте, что все возможные ветви выполнения функции возвращают значение, имеющее тип, объявленный в прототипе.  
  
3.  В функциях C\+\+, содержащих встроенные инструкции на языке ассемблера, в которых возвращаемое значение заносится в регистр `AX`, может быть необходимо использование оператора возврата.  Скопируйте значение регистра `AX` во временную переменную и верните ее из функции.  
  
 Следующий пример приводит к возникновению ошибки C2561:  
  
```  
// C2561.cpp  
int Test(int x) {  
   if (x) {  
      return;   // C2561  
      // try the following line instead  
      // return 1;  
   }  
   return 0;  
}  
  
int main() {  
   Test(1);  
}  
```