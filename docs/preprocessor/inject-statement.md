---
title: inject_statement
ms.date: 10/18/2018
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: cf7d06eddb5ae6d08f57fb82613d97c7dcc36074
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566716"
---
# <a name="injectstatement"></a>inject_statement

**Конкретных C++**

Вставляет свой аргумент как исходный текст в заголовок библиотеки типов.

## <a name="syntax"></a>Синтаксис

```
inject_statement("source_text")
```

### <a name="parameters"></a>Параметры

*source_text*<br/>
Исходный текст, вставляемый в файл заголовка библиотеки типов.

## <a name="remarks"></a>Примечания

Текст вставляется в начало объявления пространства имен, в которое помещается содержимое библиотеки типов в файле заголовка.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)