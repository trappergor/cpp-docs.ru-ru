---
title: STUB
ms.date: 11/04/2016
f1_keywords:
- STUB
helpviewer_keywords:
- STUB .def file statement
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
ms.openlocfilehash: 5224fdaa2a03dc615c9e7e7bb7f7ba822a40807e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318125"
---
# <a name="stub"></a>STUB

При использовании в файл определения модуля, который создает драйвер виртуального устройства (VxD), можно указать имя файла, который содержит структуру IMAGE_DOS_HEADER (определенную в файле WINNT. H) для использования в драйверов виртуальных устройств (VxD), а не заголовок по умолчанию.

```
STUB:filename
```

## <a name="remarks"></a>Примечания

Аналогичный способ для указания *filename* с [/STUB](stub-ms-dos-stub-file-name.md) параметр компоновщика.

ЗАГЛУШКИ является допустимым в файл определения модуля только при построении VxD.

## <a name="see-also"></a>См. также

[Правила для операторов определения модуля](rules-for-module-definition-statements.md)
