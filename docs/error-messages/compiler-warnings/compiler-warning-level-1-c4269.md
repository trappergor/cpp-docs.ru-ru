---
title: "Предупреждение компилятора (уровень 1) C4269 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4269"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4269"
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4269
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор" : константные автоматические данные, инициализируемые созданным компилятором конструктором по умолчанию, ведут к неопределенным результатам  
  
 **Константный** автоматический экземпляр нетривиального класса инициализирован конструктором, созданным по умолчанию компилятором.  
  
## Пример  
  
```  
// C4269.cpp  
// compile with: /c /LD /W1  
class X {  
public:  
   int m_data;  
};  
  
void g() {  
   const X x1;   // C4269  
};  
```  
  
 Поскольку экземпляр класса создан в стеке, начальное значение `m_data` может быть любым.  Кроме того, поскольку это **константный** экземпляр, значение `m_data` не может быть изменено.