---
title: no_smart_pointers, атрибут импорта
ms.date: 08/29/2019
f1_keywords:
- no_smart_pointers
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
ms.openlocfilehash: 1fca3eb486ff3cfc7403c38e91855b799a698782
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220701"
---
# <a name="no_smart_pointers-import-attribute"></a>no_smart_pointers, атрибут импорта

**C++Зависящ**

Отключает создание интеллектуальных указателей для всех интерфейсов в библиотеке типов.

## <a name="syntax"></a>Синтаксис

> **#import** *Библиотека типов* **no_smart_pointers**

## <a name="remarks"></a>Примечания

По умолчанию при использовании директивы `#import` пользователь получает объявление интеллектуального указателя для всех интерфейсов в библиотеке типов. Эти смарт-указатели имеют тип [_com_ptr_t](../cpp/com-ptr-t-class.md).

**КОНЕЦ C++ конкретного**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)\
[Директива #import](../preprocessor/hash-import-directive-cpp.md)
