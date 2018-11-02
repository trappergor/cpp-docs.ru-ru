---
title: no_smart_pointers
ms.date: 11/04/2016
f1_keywords:
- no_search_pointers
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
ms.openlocfilehash: 305c08497a600f602767496cba48d108335fdeb8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636986"
---
# <a name="nosmartpointers"></a>no_smart_pointers
**Конкретных C++**

Отключает создание интеллектуальных указателей для всех интерфейсов в библиотеке типов.

## <a name="syntax"></a>Синтаксис

```
no_smart_pointers
```

## <a name="remarks"></a>Примечания

По умолчанию при использовании директивы `#import` пользователь получает объявление интеллектуального указателя для всех интерфейсов в библиотеке типов. Эти интеллектуальные указатели имеют тип [класс _com_ptr_t](../cpp/com-ptr-t-class.md).

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)