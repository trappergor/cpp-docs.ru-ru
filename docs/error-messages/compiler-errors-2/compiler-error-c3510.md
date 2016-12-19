---
title: "Ошибка компилятора C3510 | Microsoft Docs"
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
  - "C3510"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3510"
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3510
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не удается обнаружить зависимую библиотеку типов "библиотека\_типов"  
  
 В директиве `#import` были использованы аргументы [no\_registry](../Topic/no_registry.md) и [auto\_search](../../preprocessor/auto-search.md), но компилятору не удалось найти библиотеку типов, на которую существует ссылка.  
  
 Для устранения этой ошибки следует убедиться, что компилятор имеет доступ ко всем библиотекам типов и библиотекам типов, на которые существуют ссылки.  
  
 Следующий пример приводит к возникновению ошибки C3510:  
  
 Предположим, что были скомпонованы две приведенные ниже библиотеки типов, и что библиотека C3510a.tlb была удалена или находится вне пути поиска.  
  
```  
// C3510a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C3510aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C3510  
   {  
      one, two, three  
   };  
};  
```  
  
 Исходный код второй библиотеки типов:  
  
```  
// C3510b.idl  
// post-build command: del /f C3510a.tlb  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
library C3510bLib  
{  
   importlib ("C3510a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
   struct S_C3510 {  
      enum E_C3510 e;  
   };  
};  
```  
  
 Код клиента:  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```