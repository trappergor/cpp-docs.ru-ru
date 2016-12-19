---
title: "Ошибка компилятора C2665 | Microsoft Docs"
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
  - "C2665"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2665"
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2665
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": ни одна из перегрузок "номер\_1" не может преобразовать параметр "номер\_2" из типа "тип"  
  
 Параметр перегруженной функции не может быть преобразован в требуемый тип.  Возможные способы разрешения:  
  
-   Введите оператор преобразования.  
  
-   Используйте явное преобразование.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2665.  
  
```  
// C2665.cpp  
void func(short, char*){}  
void func(char*, char*){}  
  
int main() {  
   func(0, 1);   // C2665  
   func((short)0, (char*)1);   // OK  
}  
```