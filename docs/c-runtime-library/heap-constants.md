---
title: Константы кучи
ms.date: 11/04/2016
f1_keywords:
- _HEAPBADPTR
- _HEAPEMPTY
- _HEAPBADBEGIN
- _HEAPOK
- _HEAPBADNODE
- _HEAPEND
helpviewer_keywords:
- _HEAPOK constants
- _HEAPEND constants
- HEAPBADBEGIN constants
- _HEAPBADNODE constants
- HEAPBADNODE constants
- HEAPBADPTR constants
- _HEAPEMPTY constants
- HEAPEND constants
- HEAPOK constants
- HEAPEMPTY constants
- _HEAPBADBEGIN constants
- _HEAPBADPTR constants
- heap constants
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
ms.openlocfilehash: 9419ae53cd04812f45f5feeee73fa0f89c408a0c
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522302"
---
# <a name="heap-constants"></a>Константы кучи

## <a name="syntax"></a>Синтаксис

```

#include <malloc.h>
```

## <a name="remarks"></a>Примечания

Эти константы предоставляют возвращаемое значение, отображающее состояние кучи.

|Константа|Значение|
|--------------|-------------|
|`_HEAPBADBEGIN`|Начальные сведения о заголовке не найдены или недопустимы.|
|`_HEAPBADNODE`|Обнаружен недопустимый узел или куча повреждена.|
|`_HEAPBADPTR`|Поле **_pentry** структуры **_HEAPINFO** не содержит допустимого указателя на кучу (только для подпрограммы `_heapwalk`).|
|`_HEAPEMPTY`|Куча не инициализирована.|
|`_HEAPEND`|Конец кучи успешно достигнут (только для подпрограммы `_heapwalk`).|
|`_HEAPOK`|Куча согласована (только для подпрограмм `_heapset` и `_heapchk`). Пока без ошибок: структура **_HEAPINFO** содержит сведения о следующей записи (только для подпрограммы `_heapwalk`).|

## <a name="see-also"></a>См. также

[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapset](../c-runtime-library/heapset.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)<br/>
[Глобальные константы](../c-runtime-library/global-constants.md)