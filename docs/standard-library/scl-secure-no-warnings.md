---
title: "_SCL_SECURE_NO_WARNINGS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SCL_SECURE_NO_DEPRECATE"
  - "_SCL_SECURE_NO_WARNINGS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_SCL_SECURE_NO_DEPRECATE"
  - "_SCL_SECURE_NO_WARNINGS"
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# _SCL_SECURE_NO_WARNINGS
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вызов любого из потенциально опасных методов в стандартной библиотеке C\+\+ C приведет к [Предупреждение компилятора \(уровень 3\) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md).  Чтобы отключить это предупреждение, определить макрос **\_SCL\_SECURE\_NO\_WARNINGS** в коде:  
  
```  
#define _SCL_SECURE_NO_WARNINGS  
```  
  
## Заметки  
 Другие способы отключения предупреждения C4996 включают:  
  
-   С помощью параметра компилятора [Определения препроцессора \(\/D\)](../build/reference/d-preprocessor-definitions.md):  
  
    ```  
    cl /D_SCL_SECURE_NO_WARNINGS [other compiler options] myfile.cpp  
    ```  
  
-   С помощью параметра компилятора [\/w](../build/reference/compiler-option-warning-level.md):  
  
    ```  
    cl /wd4996 [other compiler options] myfile.cpp  
    ```  
  
-   С помощью директивы [\#pragma warning](../preprocessor/warning.md):  
  
    ```  
    #pragma warning(disable:4996)  
    ```  
  
 Кроме того, можно вручную изменить уровень предупреждения C4996 с параметром компилятора **\/w\<l\>\<n\>**.  Например, задание предупреждения C4996 к уровню 4:  
  
```  
cl /w44996 [other compiler options] myfile.cpp  
```  
  
 Для получения дополнительной информации см. [\/w, \/Wn, \/WX, \/Wall, \/wln, \/wdn, \/wen, \/won \(уровень предупреждений\)](../build/reference/compiler-option-warning-level.md).  
  
## См. также  
 [Безопасные библиотеки: стандартная библиотека C\+\+](../standard-library/safe-libraries-cpp-standard-library.md)