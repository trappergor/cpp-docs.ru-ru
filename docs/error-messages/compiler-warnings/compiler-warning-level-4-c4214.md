---
title: "Предупреждение компилятора (уровень 4) C4214 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4214"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4214"
ms.assetid: 9b8db279-1f12-4a6b-a923-2db22acd1947
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 4) C4214
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использовано нестандартное расширение : типы битового поля отличны от int  
  
 В управляемых расширениях \(параметр \/Ze\) битовые поля, являющиеся членами структуры, могут иметь любой целочисленный тип.  
  
## Пример  
  
```  
// C4214.c  
// compile with: /W4  
struct bitfields  
{  
   unsigned short j:4;  // C4214  
};  
  
int main()  
{  
}  
```  
  
 Такие битовые поля недопустимы в режиме совместимости с ANSI \(параметр [\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).