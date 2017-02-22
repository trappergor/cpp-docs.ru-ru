---
title: "Предупреждение компилятора (уровень 1) C4399 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4399"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4399"
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Предупреждение компилятора (уровень 1) C4399
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"символ": при компиляции с параметром \/clr:pure символ для каждого процесса не следует помечать при помощи \_\_declspec\(dllimport\)  
  
 Данные из собственного изображения или машинных конструкций \(и конструкций CLR\) не могут быть импортированы в чистое изображение.  Чтобы устранить данное предупреждение, необходимо либо выполнять компиляцию с помощью **\/clr** \(а не **\/clr:pure**\), либо удалить `__declspec(dllimport)`.  
  
## Пример  
 В следующем примере возникает ошибка C4399.  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```