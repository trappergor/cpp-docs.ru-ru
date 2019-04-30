---
title: '&lt;strstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <strstream>
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
ms.openlocfilehash: 72b96c300aba1729823462ce6671e2f9a5285761
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412271"
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

Определяет несколько классов, поддерживающих операции iostreams для последовательностей, хранящихся в выделенном массиве **char** объекта. Такие последовательности легко преобразуются в строки C и обратно.

## <a name="syntax"></a>Синтаксис

```cpp
#include <strstream>
```

## <a name="remarks"></a>Примечания

Объекты типа `strstream` работают с `char` *, которые являются строками C. Используйте [\<sstream>](../standard-library/sstream.md) для работы с объектами типа [basic_string](../standard-library/basic-string-class.md).

> [!NOTE]
> Классы в \<strstream > являются устаревшими. Рассмотрите возможность использования классов в \<sstream > вместо этого.

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс strstreambuf](../standard-library/strstreambuf-class.md)|Этот класс описывает буфер потока, который управляет передачей элементов в и из последовательности элементов, сохраненную в **char** объект массива.|
|[Класс istrstream](../standard-library/istrstream-class.md)|Этот класс описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).|
|[Класс ostrstream](../standard-library/ostrstream-class.md)|Этот класс описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [strstreambuf](../standard-library/strstreambuf-class.md).|
|[Класс strstream](../standard-library/strstream-class.md)|Этот класс описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).|

## <a name="see-also"></a>См. также

[\<strstream>](../standard-library/strstream.md)<br/>
[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
