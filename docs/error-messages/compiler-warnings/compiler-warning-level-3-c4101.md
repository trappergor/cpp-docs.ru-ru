---
title: "Предупреждение компилятора (уровень 3) C4101 | Microsoft Docs"
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
  - "C4101"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4101"
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 3) C4101
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор" : неиспользованная локальная переменная  
  
 Локальная переменная не используется.  Это предупреждение возникает в очевидной ситуации:  
  
```  
// C4101a.cpp  
// compile with: /W3  
int main() {  
int i;   // C4101  
}  
```  
  
 Однако это предупреждение также может возникнуть при вызове функции\-члена **static** через экземпляр класса:  
  
```  
// C4101b.cpp  
// compile with:  /W3  
struct S {  
   static int func()  
   {  
      return 1;  
   }  
};  
  
int main() {  
   S si;   // C4101, si is never used  
   int y = si.func();  
   return y;  
}  
```  
  
 В этом случае компилятор использует сведения о `si` для доступа к функции **static**, но для вызова функции **static** экземпляр класса не требуется; поэтому и возникает предупреждение.  Для решения проблемы можно:  
  
-   Добавить конструктор, в котором компилятор будет использовать экземпляр `si` в вызове `func`.  
  
-   Удалить ключевое слово **static** из определения `func`.  
  
-   Вызвать функцию **static** явно: `int y = S::func();`.