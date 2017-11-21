---
title: "Как: использование преобразователя в конвейере данных | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- transformer class, example
- data pipelines, using transformer [Concurrency Runtime]
- using transformer in data pipelines [Concurrency Runtime]
ms.assetid: ca49cb3f-4dab-4b09-a9c9-d3a109ae4c29
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 97591a66f7499e136072d47e2a7c5b87870a4702
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-transformer-in-a-data-pipeline"></a>Практическое руководство. Использование преобразователя в конвейере данных
В этом разделе содержится базовый пример, демонстрирующий использование [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) в конвейере данных. Более полный пример, в котором для выполнения обработки изображений используется конвейер данных, в разделе [Пошаговое руководство: создание сети обработки изображений](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).  
  
 *Конвейеризация данных* — это общий шаблон в параллельном программировании. Конвейер данных состоит из нескольких этапов, где каждый этап выполняет работу, а затем передает результат этой работы на следующий этап. `transformer` Класс данных является ключевым компонентом конвейеров, так как он получает входное значение, выполняет работу с этим значением и затем выдает результат для другим компонентом.  
  
## <a name="example"></a>Пример  
 В этом примере используется следующий конвейер данных для выполнения ряда преобразований с начальным входным значением:  
  
1.  На первом этапе вычисляется абсолютное значение входного потока.  
  
2.  На втором этапе вычисляется квадратный корень из входного потока.  
  
3.  На третьем этапе вычисляется квадрат входных данных.  
  
4.  Д инвертирует входных данных в рабочей области.  
  
5.  Пятый этап окончательный результат записывается в буфер сообщений.  
  
 Наконец в примере выводится результат конвейера в консоль.  
  
 [!code-cpp[concrt-data-pipeline#1](../../parallel/concrt/codesnippet/cpp/how-to-use-transformer-in-a-data-pipeline_1.cpp)]  
  
 В этом примере выводятся следующие данные:  
  
```Output  
The result is -42.  
```  
  
 Чаще всего для стадии в конвейере данных для вывода значения, тип которого отличается от его входное значение. В этом примере второй этап принимает значение типа `int` качестве входных данных и создает квадратный корень из этого значения ( `double`) в качестве результата.  
  
> [!NOTE]
>  Конвейер данных в этом примере — для иллюстрации. Так как каждая операция преобразования выполняет небольшую работу, дополнительная нагрузка, необходимая для выполнения передачи сообщений, могут перевесить преимущества использования конвейера данных.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или вставить его в файл с именем `data-pipeline.cpp` , а затем запустите следующую команду в окне командной строки Visual Studio.  
  
 **CL.exe/EHsc data-pipeline.cpp**  
  
## <a name="see-also"></a>См. также  
 [Библиотека асинхронных агентов](../../parallel/concrt/asynchronous-agents-library.md)   
 [Асинхронные блоки сообщений](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Пошаговое руководство. Создание сети обработки изображений](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)

