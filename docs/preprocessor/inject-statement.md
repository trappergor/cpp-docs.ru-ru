---
title: inject_statement
ms.date: 10/18/2018
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: 237ca796028aad7aff55442eb2806fe400330a29
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034291"
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