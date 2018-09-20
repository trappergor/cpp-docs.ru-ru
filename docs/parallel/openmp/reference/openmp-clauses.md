---
title: Предложения OpenMP | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: afd0a8f66f9b0d027671629998597955b3aa69e9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378339"
---
# <a name="openmp-clauses"></a>Предложения OpenMP

Ссылки на предложения, используемые в OpenMP API.

Visual C++ поддерживает следующие предложения OpenMP.

|Предложение|Описание|
|------------|-----------------|
|[copyin](../../../parallel/openmp/reference/copyin.md)|Позволяет потокам для доступа к значение главного потока для [threadprivate](../../../parallel/openmp/reference/threadprivate.md) переменной.|
|[copyprivate](../../../parallel/openmp/reference/copyprivate.md)|Указывает, что один или несколько переменных следует использовать совместно используются всеми потоками.|
|[default](../../../parallel/openmp/reference/default-openmp.md)|Задает поведение неограниченного переменных в параллельной области.|
|[firstprivate](../../../parallel/openmp/reference/firstprivate.md)|Указывает, что каждый поток должен иметь свой собственный экземпляр переменной, и что переменная должна быть инициализирована со значением переменной, так как она существует до параллельной конструкции.|
|[if](../../../parallel/openmp/reference/if-openmp.md)|Указывает, следует ли выполнять цикл параллельно или последовательно.|
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|Указывает, что версия переменной в охватывающем контексте приравнивается к закрытой версии потока, который выполняет последней итерации (конструкция цикл "for") или последний раздел (#pragma разделов).|
|[nowait](../../../parallel/openmp/reference/nowait.md)|Переопределяет неявное в директиве барьера.|
|[num_threads](../../../parallel/openmp/reference/num-threads.md)|Задает количество потоков в группе потоков.|
|[Упорядоченные](../../../parallel/openmp/reference/ordered-openmp-clauses.md)|Требуется на параллельный [для](../../../parallel/openmp/reference/for-openmp.md) инструкции Если [упорядоченные](../../../parallel/openmp/reference/ordered-openmp-directives.md) директива будет использоваться в цикле.|
|[private](../../../parallel/openmp/reference/private-openmp.md)|Указывает, что каждый поток должен иметь свой собственный экземпляр переменной.|
|[reduction](../../../parallel/openmp/reference/reduction.md)|Указывает, что один или несколько переменных, которые принадлежат к каждому потоку предметом операцию редукции в конце область параллельной обработки.|
|[schedule](../../../parallel/openmp/reference/schedule.md)|Применяется к [для](../../../parallel/openmp/reference/for-openmp.md) директива.|
|[Общие](../../../parallel/openmp/reference/shared-openmp.md)|Указывает, что один или несколько переменных следует использовать совместно используются всеми потоками.|

## <a name="see-also"></a>См. также

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)<br/>
[Директивы](../../../parallel/openmp/reference/openmp-directives.md)