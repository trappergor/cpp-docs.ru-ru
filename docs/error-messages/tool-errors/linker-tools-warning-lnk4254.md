---
title: "Предупреждение средств компоновщика LNK4254 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4254"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4254"
ms.assetid: 6f41dfb3-ca21-40d3-bac7-b637e578efa4
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Предупреждение средств компоновщика LNK4254
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

выполнено слияние раздела "раздел 1" \(смещение\) с "раздел 2" \(смещение\) с разными атрибутами  
  
 Выполнено слияние содержимого одного раздела с содержимым другого раздела, но атрибуты двух разделов различаются.  Программа может выдать непрогнозируемый результат.  Например, данные, которым необходимо присвоить атрибут "только для чтения", могут оказаться в разделе с данными, доступными для записи.  
  
 Для устранения ошибки LNK4254 следует изменить или удалить запрос на слияние.  
  
 При разработке кода для 32\-разрядных компьютеров и целевых объектов Windows CE \(ARM, MIPS, SH4 и Thumb\) с помощью Visual C\+\+ раздел .CRT доступен только для чтения.  Если код зависит от предыдущего поведения \(разделы .CRT доступны для чтения и записи\), можно наблюдать непредвиденное поведение.  
  
 Дополнительные сведения см. в следующих разделах:  
  
-   [\/MERGE \(Слияние разделов\)](../../build/reference/merge-combine-sections.md)  
  
-   [комментарий](../../preprocessor/comment-c-cpp.md)  
  
## Пример  
 Следующий пример демонстрирует причины возникновения ошибки LNK4254.  
  
```  
// LNK4254.cpp  
// compile with: /W1 /link /WX  
// LNK4254 expected  
#pragma comment(linker, "/merge:.data=.text")  
int main() {}  
```