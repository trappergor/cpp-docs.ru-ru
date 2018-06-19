---
title: '&lt;streambuf&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <streambuf>
dev_langs:
- C++
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f4f2b455b362bcb170a09c89a0bfef8013286971
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855270"
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
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|Специализация `basic_streambuf`, использующая `char` в качестве параметров шаблона.|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|Специализация `basic_streambuf`, использующая `wchar_t` в качестве параметров шаблона.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс basic_streambuf](http://msdn.microsoft.com/en-us/d9c706ba-ce01-43e0-b0b2-a558fc53ea8d)|Этот класс шаблона описывает абстрактный базовый класс для получения буфера потока, который управляет передачей элементов в определенное представление потока и из него.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
