---
title: /LINKERMEMBER
ms.date: 11/04/2016
f1_keywords:
- /linkermember
helpviewer_keywords:
- /LINKERMEMBER dumpbin option
- LINKERMEMBER dumpbin option
- -LINKERMEMBER dumpbin option
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
ms.openlocfilehash: a0456fd9ed1729b4a6cfa200a54ba211a64e94ea
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813283"
---
# <a name="linkermember"></a>/LINKERMEMBER

```
/LINKERMEMBER[:{1|2}]
```

## <a name="remarks"></a>Примечания

Этот параметр отображает открытые символы, определенные в библиотеке. Аргумент 1 для отображения символов в порядке объекта, а также их смещения. Аргумент 2 позволяет вывести смещения и порядковые номера объектов, а затем список символов в алфавитном порядке, вместе с индексом для каждого объекта. Чтобы получить обоих выходов, укажите/LINKERMEMBER без числовой аргумент.

Только [/Headers](headers.md) параметр (программа DUMPBIN) доступен для использования в файлах, созданных с помощью [/GL](gl-whole-program-optimization.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](dumpbin-options.md)
