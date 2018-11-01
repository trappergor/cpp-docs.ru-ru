---
title: 2.6.3 Директива barrier
ms.date: 11/04/2016
ms.assetid: 4485a3d7-533f-4fec-8128-a131bec7fa16
ms.openlocfilehash: 9079dce4b2a27e91e349fd0df8414d38cd245d2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637025"
---
# <a name="263-barrier-directive"></a>2.6.3 Директива barrier

**Барьера** директива синхронизирует все потоки в команде. При обнаружении каждый поток в группе ожидает, пока не всех остальных достигли этой точки. Синтаксис **барьера** директива выглядит следующим образом:

```
#pragma omp barrier new-line
```

После всех потоков в группе столкнулись барьера, каждый поток в команде начинается выполнение инструкций после директивы барьер в параллельном режиме. Обратите внимание, что поскольку **барьера** директива не поддерживает инструкцию языка C, как часть его синтаксис, существуют некоторые ограничения на его размещения в программе. См. в разделе [приложении C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) для формальная грамматика. В примере ниже показаны эти ограничения.

```
/* ERROR - The barrier directive cannot be the immediate
*          substatement of an if statement
*/
if (x!=0)
   #pragma omp barrier
...

/* OK - The barrier directive is enclosed in a
*      compound statement.
*/
if (x!=0) {
   #pragma omp barrier
}
```