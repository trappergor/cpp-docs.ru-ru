---
title: "managed, unmanaged | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.unmanaged"
  - "managed_CPP"
  - "unmanaged_CPP"
  - "vc-pragma.managed"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "управляемая прагма"
  - "прагмы, управляемая"
  - "прагмы, неуправляемые"
  - "неуправляемая прагма"
ms.assetid: f072ddcc-e1ec-408a-8ce1-326ddb60e4a4
caps.latest.revision: 15
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# managed, unmanaged
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Позволяет на уровне функций контролировать режим их компиляции: с управляемым или неуправляемым кодом.  
  
## Синтаксис  
  
```  
  
        #pragma managed  
#pragma unmanaged  
#pragma managed([push,] on | off)  
#pragma managed(pop)  
```  
  
## Заметки  
 Параметр компилятора [\/clr](../build/reference/clr-common-language-runtime-compilation.md) позволяет управлять режимом компиляции функций \(управляемый или неуправляемый код\) на уровне модуля.  
  
 Неуправляемая функция компилируется для собственной платформы, и среда CLR передает выполнение этой части программы в собственную платформу.  
  
 При использовании параметра **\/clr** по умолчанию функции компилируются как управляемые.  
  
 При применении этих директив pragma выполните следующие действия.  
  
-   Добавляйте директиву \#pragma перед функцией, а не в теле функции.  
  
-   Добавьте директиву pragma после операторов `#include`.  Не используйте эти директивы pragma перед операторами `#include`.  
  
 Компилятор игнорирует директивы \#pragma `managed` и `unmanaged`, если при компиляции не используется параметр **\/clr**.  
  
 При создании экземпляра шаблонной функции режим ее компиляции \(управляемый или неуправляемый код\) определяется состоянием этой директивы \#pragma в момент определения шаблона.  
  
 Дополнительные сведения см. в статье [Инициализация смешанных сборок](../Topic/Initialization%20of%20Mixed%20Assemblies.md).  
  
## Пример  
  
```  
// pragma_directives_managed_unmanaged.cpp  
// compile with: /clr  
#include <stdio.h>  
  
// func1 is managed  
void func1() {  
   System::Console::WriteLine("In managed function.");  
}  
  
// #pragma unmanaged  
// push managed state on to stack and set unmanaged state  
#pragma managed(push, off)  
  
// func2 is unmanaged  
void func2() {  
   printf("In unmanaged function.\n");  
}  
  
// #pragma managed  
#pragma managed(pop)  
  
// main is managed  
int main() {  
   func1();  
   func2();  
}  
```  
  
  **В управляемой функции.  В неуправляемой функции.**    
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)