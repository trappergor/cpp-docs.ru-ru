---
title: '&lt;strstream&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <strstream>
dev_langs:
- C++
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 882248ab4f9ed692aa36bac5873251867b2fff54
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856639"
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

Определяет несколько классов, поддерживающих операции iostreams для  последовательностей, хранящихся в выделенном массиве объекта `char`. Такие последовательности легко преобразуются в строки C и обратно.

## <a name="syntax"></a>Синтаксис

```cpp
#include <strstream>

```

## <a name="remarks"></a>Примечания

Объекты типа `strstream` работают с `char` *, которые являются строками C. Используйте [\<sstream>](../standard-library/sstream.md) для работы с объектами типа [basic_string](../standard-library/basic-string-class.md).

> [!NOTE]
> Классы в \<strstream > являются устаревшими. Рассмотрите возможность использования классов в \<sstream > вместо него.

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс strstreambuf](../standard-library/strstreambuf-class.md)|Этот класс описывает буфер потока, который управляет передачей элементов из последовательности элементов, содержащейся в объекте массива `char`, и в эту последовательность.|
|[Класс istrstream](../standard-library/istrstream-class.md)|Этот класс описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).|
|[Класс ostrstream](../standard-library/ostrstream-class.md)|Этот класс описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [strstreambuf](../standard-library/strstreambuf-class.md).|
|[Класс strstream](../standard-library/strstream-class.md)|Этот класс описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [strstreambuf](../standard-library/strstreambuf-class.md).|

## <a name="see-also"></a>См. также

[\<strstream>](../standard-library/strstream.md)<br/>
[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
