---
title: no_auto_exclude
ms.date: 11/04/2016
f1_keywords:
- no_auto_exclude
helpviewer_keywords:
- no_auto_exclude attribute
ms.assetid: 3241ef9c-758a-4e86-bdc5-37da6072430f
ms.openlocfilehash: 06bde7535bd181057750ab9dd4c3999321b4990c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038946"
---
# <a name="noautoexclude"></a>no_auto_exclude
**Блок, относящийся только к языку C++**

Отключает автоматическое исключение.

## <a name="syntax"></a>Синтаксис

```
no_auto_exclude
```

## <a name="remarks"></a>Примечания

Библиотеки типов могут содержать определения элементов, которые определены в системных заголовочных файлах или других библиотеках типов. `#import` попытки избежать несколько ошибок для определения, автоматически исключая такие элементы. Если это сделано, [Предупреждение компилятора (уровень 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md) будут выдаваться для каждого элемента, должны быть исключены. Отменить такое автоматическое исключение можно при помощи данного атрибута.

**Завершение блока, относящегося только к языку C++**

## <a name="see-also"></a>См. также

[Атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[Директива #import](../preprocessor/hash-import-directive-cpp.md)