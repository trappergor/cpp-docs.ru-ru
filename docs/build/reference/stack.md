---
title: -СТЕКА | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /stack
dev_langs:
- C++
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d8deb3e3bedcb773aa01ae5f1c3ff66ce9d509f2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716671"
---
# <a name="stack"></a>/STACK

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>Примечания

Этот параметр задает размер стека в байтах и принимает аргументы в десятичной нотации или языка C нотации. Параметр/Stack применяется только к исполняемым файлом.

*Зарезервировать* аргумент задает все выделение стека в виртуальной памяти. EDITBIN округляет указанное значение до ближайшего 4 байт.

Необязательный `commit` аргумент интерпретируется операционной системой. В Windows NT, Windows 95 и Windows 98 `commit` указывает объем физической памяти для одновременного выделения. Выделенной виртуальной памяти резервирует пространство в файле подкачки. Более высокий `commit` значение экономит время, когда приложению требуется больше пространства стека, однако увеличивает требования к памяти и, возможно, время запуска.

## <a name="see-also"></a>См. также

[Параметры EDITBIN](../../build/reference/editbin-options.md)