---
title: "Предупреждение компилятора (уровень 4) C4032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4032"
ms.assetid: 70dd0c85-0239-43f9-bb06-507f6a57d206
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

формальный параметр "число" имеет другой тип после расширения  
  
 Тип параметра несовместим с типом в предыдущем объявлении при использовании установленных по умолчанию повышений типа.  
  
 Это сообщение имеет статус ошибки в ANSI C \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\) и статус предупреждения в расширениях Microsoft \(\/Ze\).  
  
## Пример  
  
```  
// C4032.c  
// compile with: /W4  
void func();  
void func(char);   // C4032, char promotes to int  
  
int main()  
{  
}  
```