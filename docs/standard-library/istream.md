---
title: '&lt;istream&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- istream/std::<istream>
- <istream>
- std::<istream>
dev_langs:
- C++
helpviewer_keywords:
- istream header
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6ed7f0eabe0fb67177197f8bb30eb258acd0e38f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ltistreamgt"></a>&lt;istream&gt;

Определяет класс шаблона basic_istream, отвечающий за извлечение для iostreams, и класс шаблона basic_iostream, отвечающий за вставку и извлечение. Заголовок также определяет связанный манипулятор. Этот файл заголовок обычно автоматически включается другим заголовком iostreams, его редко приходится включать напрямую.

## <a name="syntax"></a>Синтаксис

```cpp
#include <istream>

```

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[iostream](../standard-library/istream-typedefs.md#iostream)|Тип `basic_iostream`, специализированный для `char`.|
|[istream](../standard-library/istream-typedefs.md#istream)|Тип `basic_istream`, специализированный для `char`.|
|[wiostream](../standard-library/istream-typedefs.md#wiostream)|Тип `basic_iostream`, специализированный для **wchar**.|
|[wistream](../standard-library/istream-typedefs.md#wistream)|Тип `basic_istream`, специализированный для **wchar**.|

### <a name="manipulators"></a>Манипуляторы

|||
|-|-|
|[ws](../standard-library/istream-functions.md#ws)|Пропускает пробелы в потоке.|
|[swap](../standard-library/istream-functions.md#istream_swap)|Меняет местами два объекта потоков.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор>>](../standard-library/istream-operators.md#op_gt_gt)|Извлекает символы и строки из потока.|

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[basic_iostream](../standard-library/basic-iostream-class.md)|Класс потока, поддерживающий ввод и вывод.|
|[basic_istream](../standard-library/basic-istream-class.md)|Класс шаблона описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока с элементами типа **Elem**, также известных как [char_type](../standard-library/basic-ios-class.md#char_type). Их признаки символов определяются классом **Tr**, также известным как [traits_type](../standard-library/basic-ios-class.md#traits_type).|

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
