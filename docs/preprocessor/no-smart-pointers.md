---
title: no_smart_pointers
ms.date: 11/04/2016
f1_keywords:
- no_search_pointers
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
ms.openlocfilehash: ed4950b9e90ef968fcf0c42e4f0a9775c58ea7ec
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030171"
---
# <a name="nosmartpointers"></a>no_smart_pointers
**Блок, относящийся только к языку C++**

Отключает создание интеллектуальных указателей для всех интерфейсов в библиотеке типов.

## <a name="syntax"></a>Синтаксис

```
no_smart_pointers
```

## <a name="remarks"></a>Примечания

По умолчанию при использовании директивы `#import` пользователь получает объявление интеллектуального указателя для всех интерфейсов в библиотеке типов. Эти интеллектуальные указатели имеют тип [класс _com_ptr_t](../cpp/com-ptr-t-class.md).

**Завершение блока, относящегося только к языку C++**

## <a name="see-also"></a>См. также

[Атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[Директива #import](../preprocessor/hash-import-directive-cpp.md)