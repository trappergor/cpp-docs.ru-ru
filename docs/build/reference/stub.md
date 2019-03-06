---
title: STUB
ms.date: 11/04/2016
f1_keywords:
- STUB
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
ms.openlocfilehash: fd2e7c4a3bd9fa09b88f4c3caa9b7d5b73c1ad98
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412943"
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
