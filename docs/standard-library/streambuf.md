---
title: '&lt;streambuf&gt;'
ms.date: 11/04/2016
f1_keywords:
- <streambuf>
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
ms.openlocfilehash: 87fb74f62abffdd62b8c0179b13f53d96439d6c6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449569"
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
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|Специализация `basic_streambuf` , в которой в качестве параметров шаблона используется **char** .|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|Специализация `basic_streambuf` , которая использует **wchar_t** в качестве параметров шаблона.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс basic_streambuf](basic-streambuf-class.md)|Этот класс шаблона описывает абстрактный базовый класс для получения буфера потока, который управляет передачей элементов в определенное представление потока и из него.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostreams](../standard-library/iostreams-conventions.md)
