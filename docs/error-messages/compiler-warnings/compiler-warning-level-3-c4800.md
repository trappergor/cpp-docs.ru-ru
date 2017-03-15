---
title: "Предупреждение компилятора (уровень 3) C4800 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4800"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4800"
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 3) C4800
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": принудительно задано логическое значение "true" или "false" \(предупреждение о производительности\)  
  
 Данное предупреждение вызывается в случае, когда значение, не являющееся значением `bool`, присваивается или преобразуется в тип `bool`.  Как правило, сообщение о предупреждении выводится в результате назначения переменных `int` переменным `bool`, где переменные `int` содержат только значения **true** и **false**, и их можно повторно объявить как тип `bool`.  Если невозможно перезаписать выражение для использования типа `bool`, можно добавить к выражению "`!=0`", что присваивает выражению тип `bool`.  Приведение выражения к типу `bool`, вопреки намерениям, не устраняет предупреждение.  
  
 Следующий пример приводит к возникновению ошибки C4800:  
  
```  
// C4800.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
  
   // try..  
   // bool i = 0;  
  
   bool j = i;   // C4800  
   j++;  
}  
```