---
title: _ITERATOR_DEBUG_LEVEL | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
dev_langs:
- C++
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b317358a00879d4430b94ea29ab547761044e56
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="iteratordebuglevel"></a>_ITERATOR_DEBUG_LEVEL

Макрос `_ITERATOR_DEBUG_LEVEL` управляет включением [проверенных итераторов](../standard-library/checked-iterators.md) и [поддержки отладки итераторов ](../standard-library/debug-iterator-support.md). Этот макрос заменяет и объединяет функциональные возможности более старых макросов `_SECURE_SCL` и `_HAS_ITERATOR_DEBUGGING`.

## <a name="macro-values"></a>Значение макроса

В следующей таблице описаны возможные значения макроса `_ITERATOR_DEBUG_LEVEL`.

|Режим компиляции|Значение макроса|Описание|
|----------------------|----------------|-----------------|
|**Отладка**|||
||0|Отключает проверенные итераторы и отключает отладку итераторов.|
||1|Включает проверенные итераторы и отключает отладку итераторов.|
||2 (по умолчанию)|Включает отладку итераторов; проверенные итераторы не имеют значения.|
|**Релиз**|||
||0 (по умолчанию)|Отключает проверенные итераторы.|
||1|Включает проверенные итераторы; отладка итераторов не имеет значения.|

В режиме релиза компилятор создает ошибку, если указать `_ITERATOR_DEBUG_LEVEL` как 2.

## <a name="remarks"></a>Примечания

Макрос `_ITERATOR_DEBUG_LEVEL` управляет включением [проверенных итераторов](../standard-library/checked-iterators.md) и [поддержки отладки итераторов ](../standard-library/debug-iterator-support.md). Если `_ITERATOR_DEBUG_LEVEL` определен как 1 или 2, проверенные итераторы гарантируют, что границы ваших контейнеров не будут перезаписаны. Если `_ITERATOR_DEBUG_LEVEL` равно 0, итераторы не проверяются. Если `_ITERATOR_DEBUG_LEVEL` определен как 1, любое небезопасное использование итераторов вызовет ошибку во время выполнения и программа будет завершена. Когда `_ITERATOR_DEBUG_LEVEL` определяется как 2, небезопасное использование итератора вызывает подтверждение и появление диалогового ошибки времени выполнения, позволяющее переключиться в режим отладчика.

Так как макрос `_ITERATOR_DEBUG_LEVEL` поддерживает функциональность, аналогичную макросам `_SECURE_SCL` и `_HAS_ITERATOR_DEBUGGING`, в конкретных ситуациях нелегко решить, какие макросы и значения макросов использовать. Чтобы избежать путаницы, рекомендуется использовать только макрос `_ITERATOR_DEBUG_LEVEL`. В следующей таблице описаны эквивалентные значения макроса `_ITERATOR_DEBUG_LEVEL` для их использования при различных значениях `_SECURE_SCL` и `_HAS_ITERATOR_DEBUGGING` в существующем коде.

|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0 (значение по умолчанию для релиза)|0 (отключено)|0 (отключено)|
|1|1 (включено)|0 (отключено)|
|2 (значение по умолчанию для отладки)|(неприменимо)|1 (включено в режиме отладки)|

Сведения о том, как отключить предупреждения о проверенных итераторах, см. в разделе [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

### <a name="example"></a>Пример

Чтобы задать значение для макроса `_ITERATOR_DEBUG_LEVEL`, используйте параметр компилятора [/D](../build/reference/d-preprocessor-definitions.md), чтобы определить его в командной строке, или используйте `#define` перед тем, как заголовки стандартной библиотеки C++ будут включены в ваши исходные файлы. Например, при работе в командной строке для компиляции *sample.cpp* в режиме отладки и для использования поддержки отладки итераторов вы можете указать определение макроса`_ITERATOR_DEBUG_LEVEL`:

`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`

В исходном файле укажите макрос перед любыми заголовками стандартной библиотеки, определяющими итераторы.

```cpp
// sample.cpp

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>

// ...
```

## <a name="see-also"></a>См. также

[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[Безопасные библиотеки: стандартная библиотека C++](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
