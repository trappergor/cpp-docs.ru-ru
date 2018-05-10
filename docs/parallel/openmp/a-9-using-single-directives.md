---
title: Одной директивы Using а.9 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc0e0e08b0b7bdea05bf4c627ae33cc42298c6dc
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="a9---using-single-directives"></a>A.9   Использование отдельных директив
В следующем примере демонстрируется `single` директивы ([раздел 2.4.3](../../parallel/openmp/2-4-3-single-construct.md) на стр.). В примере, только один поток (обычно встречает первый поток `single` директива) выводит сообщения о ходе выполнения. Пользователь не должен делать никаких предположений для потока, в который будет выполняться `single` раздела. Пропускает все потоки `single` статьи и прекратит барьера в конце `single` построения. Если другие потоки могут продолжить работу без ожидания завершения потока, выполняющегося `single` разделе `nowait` предложение может быть указано в `single` директивы.  
  
```  
#pragma omp parallel  
{  
    #pragma omp single  
        printf_s("Beginning work1.\n");  
    work1();  
    #pragma omp single  
        printf_s("Finishing work1.\n");  
    #pragma omp single nowait  
        printf_s("Finished work1 and beginning work2.\n");  
    work2();  
}  
```