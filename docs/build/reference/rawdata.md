---
title: /RAWDATA
ms.date: 11/04/2016
f1_keywords:
- /rawdata
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
ms.openlocfilehash: 91fa1e26ca159f23c848efc6bf46afdea2a8bc52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621485"
---
# <a name="rawdata"></a>/RAWDATA

```
/RAWDATA[:{1|2|4|8|NONE[,number]]
```

## <a name="remarks"></a>Примечания

Этот параметр отображает необработанное содержимое каждого раздела в файле. Аргументы определяют формат отображения, как показано ниже:

|Аргумент|Результат|
|--------------|------------|
|1|По умолчанию. Содержимое отображается в шестнадцатеричных байтов, а также как символы ASCII, если они имеют печатных представление.|
|2|Содержимое отображаются в виде шестнадцатеричных значений длиной 2 байта.|
|4|Содержимое отображаются в виде шестнадцатеричных значений 4 байтам.|
|8|Содержимое отображаются в виде шестнадцатеричных значений размером 8 байт.|
|НЕТ|Необработанные данные отбрасываются. Этот аргумент полезен для управления выводом/ALL.|
|*Число*|Отображаемые строки заданы для ширины, который содержит `number` значений каждой строке.|

Только [/Headers](../../build/reference/headers.md) параметр (программа DUMPBIN) доступен для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)