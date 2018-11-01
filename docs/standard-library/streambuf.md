---
title: '&lt;streambuf&gt;'
ms.date: 11/04/2016
f1_keywords:
- <streambuf>
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
ms.openlocfilehash: 2a36658cc3cae4a05d3ca45fca619ef21c5d7c82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448832"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

Добавьте стандартный заголовок iostreams \<streambuf>, чтобы определить класс шаблона [basic_streambuf](../standard-library/basic-streambuf-class.md), который является базовым для операций классов iostreams. Этот заголовок обычно включается автоматически при использовании других заголовков потоков ввода-вывода (iostream). Его редко приходится включать напрямую.

## <a name="syntax"></a>Синтаксис

```cpp
#include <streambuf>

```

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|Специализация `basic_streambuf` , использующий **char** в качестве параметров шаблона.|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|Специализация `basic_streambuf` , использующий **wchar_t** в качестве параметров шаблона.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс basic_streambuf](basic-streambuf-class.md)|Этот класс шаблона описывает абстрактный базовый класс для получения буфера потока, который управляет передачей элементов в определенное представление потока и из него.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
