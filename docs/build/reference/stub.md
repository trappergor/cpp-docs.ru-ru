---
title: STUB
ms.date: 11/04/2016
f1_keywords:
- STUB
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
ms.openlocfilehash: 95f8e1584bdd87f23e87c27418c0debca5c3181a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533722"
---
# <a name="stub"></a>STUB

При использовании в файл определения модуля, который создает драйвер виртуального устройства (VxD), можно указать имя файла, который содержит структуру IMAGE_DOS_HEADER (определенную в файле WINNT. H) для использования в драйверов виртуальных устройств (VxD), а не заголовок по умолчанию.

```
STUB:filename
```

## <a name="remarks"></a>Примечания

Аналогичный способ для указания *filename* с [/STUB](../../build/reference/stub-ms-dos-stub-file-name.md) параметр компоновщика.

ЗАГЛУШКИ является допустимым в файл определения модуля только при построении VxD.

## <a name="see-also"></a>См. также

[Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)