---
title: "Ошибка компилятора C2026 | Microsoft Docs"
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
  - "C2026"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2026"
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2026
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

слишком большая строка, замыкающие знаки сокращены  
  
 Длина строки превышает ограничение в 16380 однобайтовых знаков.  
  
 В операции объединения строк могут включаться только строки длиной менее 16380 однобайтовых знаков.  
  
 Эта ошибка также возникает при использовании строк Юникод вдвое меньшей длины.  
  
 При следующем определении строки возникает ошибка C2026:  
  
```  
char sz[] =  
"\  
imagine a really, really \  
long string here\  
";  
```  
  
 Можно разбить строку следующим образом:  
  
```  
char sz[] =  
"\  
imagine a really, really "  
"long string here\  
";  
```  
  
 Строковые литералы большого размера \(более 32 КБ\) можно сохранить в пользовательском файле ресурсов или внешнем файле.  Дополнительные сведения см. в разделе [Создание нового пользовательского ресурса или ресурса данных](../../mfc/creating-a-new-custom-or-data-resource.md).