---
title: "Предупреждение средств компоновщика LNK4253 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4253"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4253"
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение средств компоновщика LNK4253
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

раздел 'section1' не объединен с 'section2'; уже объединен с 'section3'  
  
 Компоновщик обнаружил несколько конфликтующих запросов объединения.  Компоновщик игнорирует один из этих запросов.  
  
 Используется параметр или директива **\/MERGE** и раздел `from` уже объединен с другим разделом при предыдущем использовании параметра или директивы **\/MERGE** \(или в результате явного объединения компоновщиком\).  
  
 Для решения этой проблемы удалите один из запросов объединения.  
  
 При разработке кода для 32\-разрядных компьютеров и целевых объектов Windows CE \(ARM, MIPS, SH4 и Thumb\) с помощью Visual C\+\+ раздел .CRT теперь доступен только для чтения.  Если функционирование кода зависит от предыдущего поведения \(разделы .CRT имеют атрибуты "запись и чтение"\), вероятно непрогнозируемое поведение.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [\/MERGE \(Слияние разделов\)](../../build/reference/merge-combine-sections.md)  
  
-   [комментарий](../../preprocessor/comment-c-cpp.md)  
  
## Пример  
 В следующем примере компоновщик объединяет раздел `.rdata` дважды, но с разными разделами.  Следующий пример приводит к возникновению предупреждения LNK4253.  
  
```  
// LNK4253.cpp  
// compile with: /W1 /link /merge:.rdata=text2  
// LNK4253 expected  
#pragma comment(linker, "/merge:.rdata=.text")  
int main() {}  
```