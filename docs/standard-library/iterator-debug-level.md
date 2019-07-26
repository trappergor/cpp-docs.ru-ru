---
title: _ITERATOR_DEBUG_LEVEL
ms.date: 11/04/2016
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
ms.openlocfilehash: 7b573127518969accdfdcc4a25a50269dd6aa002
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456398"
---
# <a name="iteratordebuglevel"></a>_ITERATOR_DEBUG_LEVEL

Макрос _ITERATOR_DEBUG_LEVEL определяет, включены [](../standard-library/checked-iterators.md) ли проверенные итераторы и [Поддержка итератора отладки](../standard-library/debug-iterator-support.md) . Этот макрос заменяет и объединяет функциональные возможности старых макросов _SECURE_SCL и _HAS_ITERATOR_DEBUGGING.

## <a name="macro-values"></a>Значение макроса

В следующей таблице приведены возможные значения для макроса _ITERATOR_DEBUG_LEVEL.

|Режим компиляции|Значение макроса|Описание|
|----------------------|----------------|-----------------|
|**Отладка**|||
||0|Отключает проверенные итераторы и отключает отладку итераторов.|
||1|Включает проверенные итераторы и отключает отладку итераторов.|
||2 (по умолчанию)|Включает отладку итераторов; проверенные итераторы не имеют значения.|
|**Релиз**|||
||0 (по умолчанию)|Отключает проверенные итераторы.|
||1|Включает проверенные итераторы; отладка итераторов не имеет значения.|

В режиме выпуска компилятор выдает ошибку, если указать _ITERATOR_DEBUG_LEVEL как 2.

## <a name="remarks"></a>Примечания

Макрос _ITERATOR_DEBUG_LEVEL определяет, включены [](../standard-library/checked-iterators.md) ли проверенные итераторы, а также в режиме отладки, включена ли [Поддержка итераторов отладки](../standard-library/debug-iterator-support.md) . Если _ITERATOR_DEBUG_LEVEL определен как 1 или 2, проверяемые итераторы гарантируют, что границы контейнеров не перезаписываются. Если значение _ITERATOR_DEBUG_LEVEL равно 0, то итераторы не проверяются. Если _ITERATOR_DEBUG_LEVEL определен как 1, любое ненадежное использование итератора вызывает ошибку времени выполнения и программа завершается. Если _ITERATOR_DEBUG_LEVEL определен как 2, ненадежное использование итератора приводит к появлению диалогового окна "Assert" и "Error Runtime", которое позволяет переключиться на отладчик.

Так как макрос _ITERATOR_DEBUG_LEVEL поддерживает аналогичные функции для макросов _SECURE_SCL и _HAS_ITERATOR_DEBUGGING, возможно, вы не уверены, какое значение макроса и макроса использовать в конкретной ситуации. Чтобы избежать путаницы, рекомендуется использовать только макрос _ITERATOR_DEBUG_LEVEL. В этой таблице описывается эквивалентное значение макроса _ITERATOR_DEBUG_LEVEL, используемое для различных значений _SECURE_SCL и _HAS_ITERATOR_DEBUGGING в существующем коде.

|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0 (значение по умолчанию для релиза)|0 (отключено)|0 (отключено)|
|1|1 (включено)|0 (отключено)|
|2 (значение по умолчанию для отладки)|(неприменимо)|1 (включено в режиме отладки)|

Сведения о том, как отключить предупреждения о проверенных итераторах, см. в разделе [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

### <a name="example"></a>Пример

Чтобы указать значение для макроса _ITERATOR_DEBUG_LEVEL, используйте параметр компилятора [/d](../build/reference/d-preprocessor-definitions.md) для определения его в командной строке или используйте `#define` перед включением заголовков C++ стандартной библиотеки в исходные файлы. Например, чтобы скомпилировать *Sample. cpp* в режиме отладки и использовать поддержку итератора отладки, в командной строке можно указать определение макроса _ITERATOR_DEBUG_LEVEL:

`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`

В исходном файле укажите макрос перед любыми заголовками стандартной библиотеки, определяющими итераторы.

```cpp
// sample.cpp

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>

// ...
```

## <a name="see-also"></a>См. также

[Проверяемые итераторы](../standard-library/checked-iterators.md)\
[Поддержка итераторов отладки](../standard-library/debug-iterator-support.md)\
[Безопасные библиотеки: стандартная библиотека C++](../standard-library/safe-libraries-cpp-standard-library.md)
