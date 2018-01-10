---
title: "strict_gs_check | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
dev_langs: C++
helpviewer_keywords: strict_gs_check pragma
ms.assetid: decfec81-c916-42e0-a07f-8cc26df6a7ce
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5c355bd385a997e8ff3fd9ec323d50bb33b9c6fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="strictgscheck"></a>strict_gs_check
Эта директива #pragma обеспечивает усиленную проверку безопасности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma strict_gs_check([push,] on )   
#pragma strict_gs_check([push,] off )   
#pragma strict_gs_check(pop)  
```  
  
## <a name="remarks"></a>Примечания  
 Заставляет компилятор вставлять случайные объекты cookie в стек функции, помогая обнаруживать некоторые категории переполнения буфера на основе стека. По умолчанию параметр компилятора /GS (проверка безопасности буфера) обеспечивает вставку объектов cookie не для всех функций. Дополнительные сведения см. в разделе [Параметр /GS (проверка безопасности буфера)](../build/reference/gs-buffer-security-check.md).  
  
 Для включения поверки strict_gs_check необходимо выполнять компиляцию с параметром /GS (проверка безопасности буфера).  
  
 Используйте эту директиву #pragma в модулях кода, которые могут получать потенциально вредоносные данные. Эта директива #pragma отличается очень агрессивным поведением и применяется к функциям, для которых подобная защита может не требоваться, но оптимизирована с целью минимального влияния на производительность конечного приложения.  
  
 Даже при использовании этой директивы #pragma следует стремиться к созданию защищенного программного кода. Т. е убедитесь, что код не имеющий переполнений буфера. strict_gs_check может защитить приложение от переполнения буфера, которые остаются в своем коде.  
  
## <a name="example"></a>Пример  
 В следующем коде переполнение буфера возникает при копировании массива в локальный массив. Если компилировать этот код с параметром /GS, объекты cookie не помещаются в стек, поскольку тип данных массива является указателем. Добавление директивы #pragma strict_gs_check вызывает принудительное помещение объектов cookie стека в стек функции.  
  
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
  
## <a name="see-also"></a>См. также  
 [Директивы pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [Параметр /GS (проверка безопасности буфера)](../build/reference/gs-buffer-security-check.md)