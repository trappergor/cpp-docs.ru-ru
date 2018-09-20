---
title: A.29 совместной работы от использования конструкции внутри конструкции critical | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d5c8a83f-2f51-4f23-8ddf-d267e347507f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8574687d8fa037e0adca908e3aa761a2619d26a8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424148"
---
# <a name="a29---use-of-work-sharing-constructs-inside-a-critical-construct"></a>A.29   Использование конструкций совместной работы в конструкции critical

В следующем примере показано использование конструкции совместной работы внутри `critical` построения. В этом примере является совместимым, поскольку построения совместной работы и `critical` конструкция не привязываются к одной и той же параллельной области.

```
void f()
{
  int i = 1;
  #pragma omp parallel sections
  {
    #pragma omp section
    {
      #pragma omp critical (name)
      {
        #pragma omp parallel
        {
          #pragma omp single
          {
            i++;
          }
        }
      }
    }
  }
}
```