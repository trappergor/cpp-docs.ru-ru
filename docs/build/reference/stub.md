---
title: ЗАГЛУШКИ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STUB
dev_langs:
- C++
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 151d7b425a7f397a05e3a06e9d94489a0c76f899
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725118"
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