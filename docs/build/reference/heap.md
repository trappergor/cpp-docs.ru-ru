---
title: -HEAP | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /heap
dev_langs:
- C++
helpviewer_keywords:
- heap allocation, setting heap size
- HEAP editbin option
- -HEAP editbin option
- /HEAP editbin option
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 22698760ba23dc60b64002f0f728bb7a036f6731
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699820"
---
# <a name="heap"></a>/HEAP

Задает размер кучи в байтах. Этот параметр применяется только к исполняемым файлам.

```

/HEAP:
reserve[,commit]
```

## <a name="remarks"></a>Примечания

`reserve` Аргумент задает общее начальное выделение кучи виртуальной памяти. По умолчанию размер кучи составляет 1 МБ. [Справочник ЕDITBIN](../../build/reference/editbin-reference.md) Округляет указанное значение до ближайшего числа, кратного 4 байта.

Необязательный `commit` аргумент интерпретируется операционной системой. В операционной системе Windows он указывает начальный объем физической памяти для выделения, а также объем дополнительной памяти, выделяемой при кучи должна быть развернута. Выделенной виртуальной памяти резервирует пространство в файле подкачки. Более высокий `commit` значение позволяет системе для выделения памяти меньше часто в том случае, когда приложению требуется больше пространства кучи, но увеличивает требования к памяти и, возможно, на время запуска приложения. `commit` Значение должно быть меньше или равно `reserve` значение.

Укажите `reserve` и `commit` значения в десятичном или шестнадцатеричном или восьмеричном представлении нотации языка. Например значение 1 МБ можно указать как 1048576 в десятичном формате, или 0x100000 в шестнадцатеричном формате или 04000000 в восьмеричной.

## <a name="see-also"></a>См. также

[Параметры EDITBIN](../../build/reference/editbin-options.md)