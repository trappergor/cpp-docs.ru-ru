---
title: "Ошибка компилятора C2513 | Microsoft Docs"
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
  - "C2513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2513"
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": нет переменных, объявленных перед "\="  
  
 Спецификатор типа в объявлении не имеет идентификатора переменной.  
  
 Следующий пример приводит к возникновению ошибки C2513:  
  
```  
// C2513.cpp  
int main() {  
   int = 9;   // C2513  
   int i = 9;   // OK  
}  
```  
  
 Это ошибка может также возникать в результате работы согласованности компилятора для Visual Studio .NET 2003: инициализация typedef больше не допускается.  Инициализация typedef не допускается в соответствии со стандартом и приводит теперь к возникновению ошибки компилятора.  
  
```  
// C2513b.cpp  
// compile with: /c  
typedef struct S {  
   int m_i;  
} S = { 1 };   // C2513  
// try the following line instead  
// } S;  
```  
  
 В качестве альтернативы можно удалить `typedef`, чтобы определить переменную с помощью списка составных инициализаторов, однако делать это не рекомендуется, так как при этом будет создана переменная с тем же именем, что и тип, а имя типа будет скрыто.