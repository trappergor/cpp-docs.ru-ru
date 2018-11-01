---
title: Указание встроенного файла
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
ms.openlocfilehash: 8f8868ce3755bd47f779576a7e44125f53314606
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648703"
---
# <a name="specifying-an-inline-file"></a>Указание встроенного файла

Укажите две угловые скобки (<<) в команде где *filename* должен отобразиться. Угловые скобки не может быть расширения макроса.

## <a name="syntax"></a>Синтаксис

```
<<[filename]
```

## <a name="remarks"></a>Примечания

При выполнении команды, угловые скобки заменяются *filename*, если указан, или по уникальному имени сформированные NMAKE. Если указано, *filename* должны соответствовать угловые скобки без пробел или символ табуляции. Путь разрешается. Расширение не является необходимым Если *filename* указан, файл создается в текущем или указанном каталоге перезаписью файл с таким именем; в противном случае она создается в каталоге TMP (или текущем каталоге, если переменная среды TMP не определен). Если предыдущей *filename* — повторно, NMAKE заменяет предыдущий файл.

## <a name="see-also"></a>См. также

[Подставляемые файлы в Makefile](../build/inline-files-in-a-makefile.md)