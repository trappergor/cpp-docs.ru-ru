---
title: "Предупреждение компилятора (уровень 1) C4772 | Microsoft Docs"
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
  - "C4772"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4772"
ms.assetid: dafe6fd8-9faf-41f5-9d66-a55838742c14
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4772
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#import ссылается на тип из отсутствующей библиотеки типов; отсутствующий тип "тип" используется как заполнитель  
  
 На библиотеку типов была ссылка в директиве [\#import](../Topic/%23import%20Directive%20\(C++\).md).  Однако эта библиотека типов содержит ссылку на другую библиотеку типов, на которую нет ссылок в директиве `#import`.  Второй TLB\-файл компилятором не найден.  
  
 Заметьте, что компилятор не найдет библиотеки типов в различных директориях, если для указания этих директорий использован параметр компилятора [\/I \(дополнительные каталоги включения\)](../../build/reference/i-additional-include-directories.md).  Если вы хотите, чтобы компилятор нашел библиотеки типов в различных директориях, добавьте их в переменную окружения PATH.  
  
 Это предупреждение по умолчанию выдается как ошибка.  Ошибка C4772 не может быть отключена с помощью \/W0.  
  
## Пример  
 Это первая библиотека типов, необходимая для воспроизведения C4772.  
  
```  
// c4772a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C4772aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c100")]  
   enum E_C4772a  
   {  
      one, two, three  
   };  
};  
```  
  
## Пример  
 Это вторая библиотека типов, необходимая для воспроизведения C4772  
  
```  
// c4772b.idl  
// post-build command: del /f C4772a.tlb  
// C4772a.tlb is available when c4772b.tlb is built  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
library C4772bLib  
{  
   importlib ("c4772a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
   struct S_C4772b  
   {  
      enum E_C4772a e;  
   };  
};  
```  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C4772:  
  
```  
// C4772.cpp  
// assumes that C4772a.tlb is not available to the compiler  
// #import "C4772a.tlb"  
#import "C4772b.tlb"   // C4772 uncomment previous line to resolve  
                       // and make sure c4772a.tlb is on disk  
```