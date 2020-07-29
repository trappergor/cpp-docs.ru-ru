---
title: '&lt;streambuf&gt;'
ms.date: 11/04/2016
f1_keywords:
- <streambuf>
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
ms.openlocfilehash: 1121bd4e782fca57588d05fb29b5b9b6cdec18e9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215612"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

Добавьте стандартный заголовок iostream \<streambuf> для определения шаблона класса [basic_streambuf](../standard-library/basic-streambuf-class.md), который является базовым для работы классов iostream. Этот заголовок обычно включается автоматически при использовании других заголовков потоков ввода-вывода (iostream). Его редко приходится включать напрямую.

## <a name="syntax"></a>Синтаксис

```cpp
#include <streambuf>
```

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|Специализация `basic_streambuf` , которая использует **`char`** в качестве параметров шаблона.|
|[встреамбуф](../standard-library/streambuf-typedefs.md#wstreambuf)|Специализация `basic_streambuf` , которая использует **`wchar_t`** в качестве параметров шаблона.|

### <a name="classes"></a>Классы

|Class|Описание|
|-|-|
|[Класс basic_streambuf](basic-streambuf-class.md)|Шаблон класса описывает абстрактный базовый класс для получения буфера потока, который управляет передачей элементов в определенное представление потока и из него.|

## <a name="see-also"></a>См. также раздел

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Безопасность потоков в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostream](../standard-library/iostreams-conventions.md)
