---
title: Вычисление необходимых значений
ms.date: 11/04/2016
helpviewer_keywords:
- helper functions, calculating necessary values
ms.assetid: 4f037d0f-881a-4a48-a9d2-9f8872dfccb7
ms.openlocfilehash: 80c028a315669fb0032628bb86a834d429935f50
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513871"
---
# <a name="calculating-necessary-values"></a>Вычисление необходимых значений

Два критически важных фрагмента информации нужно вычислить, вспомогательная подпрограмма задержки. Для этого существуют две встроенные функции в delayhlp.cpp для вычисления данных.

- Первый вычисляет индекс текущего импорта в трех разных таблицах, (Импорт таблицы адресов (IAT), связанная таблица адресов импорта (BIAT) и несвязанную адресную таблицу импорта (UIAT)).

- Второй подсчитывает количество imports в допустимый IAT.

```cpp
// utility function for calculating the index of the current import
// for all the tables (INT, BIAT, UIAT, and IAT).
__inline unsigned
IndexFromPImgThunkData(PCImgThunkData pitdCur, PCImgThunkData pitdBase) {
    return pitdCur - pitdBase;
    }

// utility function for calculating the count of imports given the base
// of the IAT. NB: this only works on a valid IAT!
__inline unsigned
CountOfImports(PCImgThunkData pitdBase) {
    unsigned        cRet = 0;
    PCImgThunkData  pitd = pitdBase;
    while (pitd->u1.Function) {
        pitd++;
        cRet++;
        }
    return cRet;
    }
```

## <a name="see-also"></a>См. также

[Понятие вспомогательной функции](understanding-the-helper-function.md)