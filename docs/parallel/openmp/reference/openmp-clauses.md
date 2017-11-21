---
title: "Предложения OpenMP | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4de0ac69733bee42d4102edf345f69be2e5fea3f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="openmp-clauses"></a>Предложения OpenMP
Ссылки на предложения, используемые в OpenMP API.  
  
 Visual C++ поддерживает следующие предложения OpenMP:  
  
|Предложение|Описание|  
|------------|-----------------|  
|[copyin](../../../parallel/openmp/reference/copyin.md)|Позволяет потокам для доступа к значению главного потока для [threadprivate](../../../parallel/openmp/reference/threadprivate.md) переменной.|  
|[copyprivate](../../../parallel/openmp/reference/copyprivate.md)|Указывает, что один или несколько переменных должны совместно используются всеми потоками.|  
|[default](../../../parallel/openmp/reference/default-openmp.md)|Задает поведение неограниченного переменных в параллельной области.|  
|[firstprivate](../../../parallel/openmp/reference/firstprivate.md)|Указывает, что каждый поток должен иметь собственный экземпляр переменной, и что переменная должна быть инициализирована со значением переменной, так как она существует до параллельной конструкции.|  
|[if](../../../parallel/openmp/reference/if-openmp.md)|Указывает, следует ли выполнять цикл параллельно или последовательно.|  
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|Указывает, что версия контекст внешней переменной приравнивается к закрытой версии поток выполняет последней итерации (конструкция цикла for) или последний раздел (#pragma разделов).|  
|[nowait](../../../parallel/openmp/reference/nowait.md)|Переопределяет неявно в директиве барьера.|  
|[num_threads](../../../parallel/openmp/reference/num-threads.md)|Задает число потоков в поток команды.|  
|[упорядоченные](../../../parallel/openmp/reference/ordered-openmp-clauses.md)|Требуется на параллельный [для](../../../parallel/openmp/reference/for-openmp.md) инструкции Если [упорядоченные](../../../parallel/openmp/reference/ordered-openmp-directives.md) директива будет использоваться в цикле.|  
|[private](../../../parallel/openmp/reference/private-openmp.md)|Указывает, что каждый поток должен иметь собственный экземпляр переменной.|  
|[reduction](../../../parallel/openmp/reference/reduction.md)|Указывает, что одна или несколько переменных, которые принадлежат каждому потоку субъект операцию редукции в конце параллельной области.|  
|[schedule](../../../parallel/openmp/reference/schedule.md)|Применяется к [для](../../../parallel/openmp/reference/for-openmp.md) директивы.|  
|[Общие](../../../parallel/openmp/reference/shared-openmp.md)|Указывает, что один или несколько переменных должны совместно используются всеми потоками.|  
  
## <a name="see-also"></a>См. также  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Директивы](../../../parallel/openmp/reference/openmp-directives.md)