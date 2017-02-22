---
title: "Предупреждение компилятора (уровень 4) C4268 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4268"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4268"
ms.assetid: d0511e80-904f-4ee1-b4d7-39b5c0bd8234
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 4) C4268
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": статические \(глобальные\) "const"\-данные, инициализированные конструктором по умолчанию, который был создан компилятором, заполняют объект нулями  
  
 Статические или глобальные экземпляры **const** нетривиального класса инициализированы конструктором по умолчанию, созданным компилятором.  
  
## Пример  
  
```  
// C4268.cpp  
// compile with: /c /LD /W4  
class X {  
public:  
   int m_data;  
};  
  
const X x1;   // C4268  
```  
  
 Так как этот образец класса является переменной **const**, значение `m_data` не может быть изменено.