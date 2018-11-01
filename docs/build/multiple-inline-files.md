---
title: Использование нескольких встроенных файлов
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
ms.openlocfilehash: ec531e5716098725782010927201ef57e2a8aa24
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558162"
---
# <a name="multiple-inline-files"></a>Использование нескольких встроенных файлов

Команду можно создать несколько встроенных файлов.

## <a name="syntax"></a>Синтаксис

```
command << <<
inlinetext
<<[KEEP | NOKEEP]
inlinetext
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Примечания

Для каждого файла укажите один или несколько строк встроенного текста, за которым следует закрывающая строка, содержащая разделитель по. Начните второй файл текст в строке после разделителя строки, для первого файла.

## <a name="see-also"></a>См. также

[Подставляемые файлы в Makefile](../build/inline-files-in-a-makefile.md)