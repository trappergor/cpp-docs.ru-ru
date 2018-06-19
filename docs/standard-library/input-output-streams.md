---
title: Потоки ввода-вывода | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], stream
- stream I/O
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51a7a9aff4f77444bbec46a9739fae91cac3c104
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845935"
---
# <a name="inputoutput-streams"></a>Потоки ввода/вывода

`basic_iostream`, который определен в файле заголовка \<istream>, является классом шаблона для объектов, обрабатывающих потоки ввода-вывода на основе входных и выходных символов.

Существуют два определения типов, определяющие специальные для символов специализации для `basic_iostream` и упрощающие чтение кода: `iostream` (не следует путать с файлом заголовка \<iostream>) — это поток ввода-вывода, основанный на `basic_iostream<char>`; `wiostream` — это поток ввода-вывода, основанный на `basic_iostream<wchar_t>`.

Дополнительные сведения см. в разделах [Класс basic_iostream](../standard-library/basic-iostream-class.md), [iostream](../standard-library/basic-iostream-class.md) и [wiostream](../standard-library/basic-iostream-class.md).

Производным из `basic_iostream` является шаблон класса `basic_fstream`, который используется для потоковой передачи символьных данных в файлы и из них.

Также имеются определения типов, которые предоставляют специальные для символов специализации для `basic_fstream`. К ним относятся `fstream`, представляющая собой поток файлового ввода-вывода, основанный на `char`, и `wfstream`, представляющая собой поток файлового ввода-вывода, основанный на `wchar_t`. Дополнительные сведения см. в разделах [Класс basic_fstream](../standard-library/basic-fstream-class.md), [fstream](../standard-library/basic-fstream-class.md) и [wfstream](../standard-library/basic-fstream-class.md). Применение этих определений типов требует включения файла заголовка \<fstream>.

> [!NOTE]
> Если объект `basic_fstream` используется для выполнения файлового ввода-вывода, хотя базовый буфер содержит отдельно назначенные позиции для чтения и записи, текущие позиции ввода и вывода связываются друг с другом, поэтому, чтение некоторых данных перемещает позицию вывода.

Шаблон класса `basic_stringstream` и его общая специализация `stringstream` часто используются для работы с объектами потока ввода-вывода для вставки и извлечения символьных данных. Дополнительные сведения см. в разделе [Класс basic_stringstream](../standard-library/basic-stringstream-class.md).

## <a name="see-also"></a>См. также

[stringstream](../standard-library/basic-stringstream-class.md)<br/>
[Класс basic_stringstream](../standard-library/basic-stringstream-class.md)<br/>
[\<sstream>](../standard-library/sstream.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Стандартная библиотека C++](../standard-library/cpp-standard-library-reference.md)<br/>
