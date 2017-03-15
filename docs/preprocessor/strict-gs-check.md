---
title: "strict_gs_check | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "strict_gs_check"
  - "strict_gs_check_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strict_gs_check - прагма"
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# strict_gs_check
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эта директива \#pragma обеспечивает усиленную проверку безопасности.  
  
## Синтаксис  
  
```  
#pragma strict_gs_check([push,] on )   
#pragma strict_gs_check([push,] off )   
#pragma strict_gs_check(pop)  
```  
  
## Заметки  
 Заставляет компилятор вставлять случайные объекты cookie в стек функции, помогая обнаруживать некоторые категории переполнения буфера на основе стека.  По умолчанию параметр компилятора \/GS \(проверка безопасности буфера\) обеспечивает вставку объектов cookie не для всех функций.  Дополнительные сведения см. в разделе [Параметр \/GS \(проверка безопасности буфера\)](../Topic/-GS%20\(Buffer%20Security%20Check\).md).  
  
 Для включения поверки strict\_gs\_check необходимо выполнять компиляцию с параметром \/GS \(проверка безопасности буфера\).  
  
 Используйте эту директиву \#pragma в модулях кода, которые могут получать потенциально вредоносные данные.  Эта директива \#pragma отличается очень агрессивным поведением и применяется к функциям, для которых подобная защита может не требоваться, но оптимизирована с целью минимального влияния на производительность конечного приложения.  
  
 Даже при использовании этой директивы \#pragma следует стремиться к созданию защищенного программного кода.  Обязательно убедитесь, что в коде нет ошибок переполнения буфера. Проверка strict\_gs\_check может помочь защитить приложение от ошибок переполнения буфера, не обнаруженных в коде.  
  
## Пример  
 В следующем коде переполнение буфера возникает при копировании массива в локальный массив.  Если компилировать этот код с параметром \/GS, объекты cookie не помещаются в стек, поскольку тип данных массива является указателем.  Добавление директивы \#pragma strict\_gs\_check вызывает принудительное помещение объектов cookie стека в стек функции.  
  
```cpp  
// pragma_strict_gs_check.cpp  
// compile with: /c  
  
#pragma strict_gs_check(on)  
  
void ** ReverseArray(void **pData,  
                     size_t cData)  
{  
    // *** This buffer is subject to being overrun!! ***  
    void *pReversed[20];  
  
    // Reverse the array into a temporary buffer  
    for (size_t j = 0, i = cData; i ; --i, ++j)  
        // *** Possible buffer overrun!! ***  
            pReversed[j] = pData[i];   
  
    // Copy temporary buffer back into input/output buffer  
    for (size_t i = 0; i < cData ; ++i)   
        pData[i] = pReversed[i];  
  
    return pData;  
}  
  
```  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [Параметр \/GS \(проверка безопасности буфера\)](../Topic/-GS%20\(Buffer%20Security%20Check\).md)