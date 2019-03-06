---
title: Использование нескольких встроенных файлов
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
ms.openlocfilehash: 5b41d448c89ac30d891c41d1ad1e314cbf9724a8
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57425618"
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
