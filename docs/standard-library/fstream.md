---
title: '&lt;fstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: 1f85367b9ae527c9387d085acc1496bfbbf7cc9e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688039"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

Определяет несколько классов, поддерживающих операции iostreams для последовательностей, хранящихся во внешних файлах.

## <a name="syntax"></a>Синтаксис

```cpp
#include <fstream>
```

### <a name="typedefs"></a>Typedefs

|Имя типа|Описание|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Тип `basic_filebuf` специализированный для параметров шаблона **char** .|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Тип `basic_fstream` специализированный для параметров шаблона **char** .|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Тип `basic_ifstream` специализированный для параметров шаблона **char** .|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Тип `basic_ofstream` специализированный для параметров шаблона **char** .|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Тип `basic_fstream` специализированный для параметров шаблона **wchar_t** .|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Тип `basic_ifstream` специализированный для параметров шаблона **wchar_t** .|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Тип `basic_ofstream` специализированный для параметров шаблона **wchar_t** .|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Тип `basic_filebuf` специализированный для параметров шаблона **wchar_t** .|

### <a name="classes"></a>Классы

|Class|Описание|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Шаблон класса описывает буфер потока, который управляет передачей элементов типа `Elem`, признаки символов которых определяются классом `Tr`, в последовательность элементов, хранящуюся во внешнем файле, и из нее.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|Шаблон класса описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> с элементами типа `Elem`, символ которых признаки определяются классом `Tr`.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Шаблон класса описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> с элементами типа `Elem`, признаки символов которых определяется классом `Tr`.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Шаблон класса описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> с элементами типа `Elem`, признаки символов которых определяются классом `Tr`.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostreams](../standard-library/iostreams-conventions.md)
