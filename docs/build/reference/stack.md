---
title: /STACK
ms.date: 11/04/2016
f1_keywords:
- /stack
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
ms.openlocfilehash: 89591a9d0a7f19422275b6bce6f4c5a7a723e800
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647711"
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