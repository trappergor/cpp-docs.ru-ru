---
title: A.9 Использование отдельных директив | Документация Майкрософт
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
ms.openlocfilehash: 5a3a201450d54355aa96f0ea712ad9fa0f70f63f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448094"
---
# <a name="a9---using-single-directives"></a>A.9   Использование отдельных директив

В следующем примере демонстрируется `single` директива ([разделе 2.4.3](../../parallel/openmp/2-4-3-single-construct.md) на стр. 15). В примере, только один поток (обычно первый поток, у которых `single` директива) выводит сообщение о ходе выполнения. Пользователь не должен делать никаких предположений в каком потоке будет выполняться `single` раздел. Пропускает все прочие потоки `single` разделе и останавливать барьера в конце `single` построения. Если другие потоки могут продолжить работу без ожидания завершения потока, выполняющегося `single` разделе `nowait` предложение может быть указано в `single` директива.

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