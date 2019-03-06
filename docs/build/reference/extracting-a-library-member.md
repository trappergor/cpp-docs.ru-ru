---
title: Извлечение члена библиотеки
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
ms.openlocfilehash: 4d7629707d99130551401fdda39a972ab2447480
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412891"
---
# <a name="extracting-a-library-member"></a>Извлечение члена библиотеки

LIB можно использовать для создания файла объектов (OBJ), содержащий копию элемента в существующую библиотеку. Чтобы извлечь копию члена, используйте следующий синтаксис:

```
LIB library /EXTRACT:member /OUT:objectfile
```

Эта команда создает OBJ-файл называется *objectfile* , содержащий копию `member` из *библиотеки*. `member` Имя чувствительно к регистру. Можно извлечь только один элемент в рамках одной команды. Параметр/out является обязательным; отсутствует имя выходных данных по умолчанию. Если файл с именем *objectfile* уже существует в указанном каталоге (или текущем каталоге, если каталог не указан с *objectfile*), извлеченный *objectfile*заменяет существующий файл.

## <a name="see-also"></a>См. также

[Справочник по LIB](../../build/reference/lib-reference.md)
