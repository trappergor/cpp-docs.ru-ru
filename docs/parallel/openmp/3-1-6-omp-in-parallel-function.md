---
title: 3.1.6 функция omp_in_parallel | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22b491695d2ae49336d7d8998af64e724f344d87
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="316-ompinparallel-function"></a>3.1.6 Функция omp_in_parallel
**Omp_in_parallel** функция возвращает ненулевое значение, если он вызывается в пределах области динамических параллельной области параллельного выполнения; в противном случае возвращается значение 0. Он следующий:  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 Эта функция возвращает ненулевое значение, если вызвать в пределах области параллельного выполнения, включая вложенные области, которые сериализуются.