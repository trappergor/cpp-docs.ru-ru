---
title: '&lt;stdexcept&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <stdexcept>
dev_langs:
- C++
helpviewer_keywords:
- stdexcept header
ms.assetid: 495c10b1-1e60-4514-9f8f-7fda11a2f522
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c28e4bbccb3c28c314226b8f215407292d5e200
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863625"
---
# <a name="ltstdexceptgt"></a>&lt;stdexcept&gt;

Определяет несколько стандартных классов, используемых для сообщения об исключениях. Классы образуют иерархию наследования. Все они производны от класса [exception](../standard-library/exception-class.md) и включают два основных типа исключений: логические ошибки и ошибки во время выполнения. Логические ошибки — это ошибки программиста. Они являются производными от базового класса logic_error и включают:

- `domain_error`

- `invalid_argument`

- `length_error`

- `out_of_range`

Ошибки во время выполнения возникают из-за ошибок в функциях библиотеки или в системе времени выполнения. Они являются производными от базового класса runtime_error и включают:

- `overflow_error`

- `range_error`

- `underflow_error`

### <a name="classes"></a>Классы

|Класс|Описание|
|-|-|
|[Класс domain_error](../standard-library/domain-error-class.md)|Этот класс служит базовым классом для всех исключений, создаваемых для сообщения об ошибке в домене.|
|[Класс invalid_argument](../standard-library/invalid-argument-class.md)|Этот класс служит базовым классом для всех исключений, создаваемых для сообщения о недопустимом аргументе.|
|[Класс length_error](../standard-library/length-error-class.md)|Этот класс служит базовым для всех исключений, создаваемых для сообщения о попытке создания слишком длинного объекта.|
|[Класс logic_error](../standard-library/logic-error-class.md)|Этот класс служит базовым для всех исключений, создаваемых для сообщения об ошибках, которые можно обнаружить до выполнения программы, таких как нарушение логических предварительных условий.|
|[Класс out_of_range](../standard-library/out-of-range-class.md)|Этот класс служит базовым для всех исключений, создаваемых для сообщения о том, что аргумент выходит за допустимый диапазон.|
|[Класс overflow_error](../standard-library/overflow-error-class.md)|Этот класс служит базовым для всех исключений, создаваемых для сообщения об арифметическом переполнении.|
|[Класс range_error](../standard-library/range-error-class.md)|Этот класс служит базовым для всех исключений, создаваемых для сообщения об ошибке в диапазоне.|
|[Класс runtime_error](../standard-library/runtime-error-class.md)|Этот класс служит базовым для всех исключений, создаваемых для сообщения об ошибках, которые можно обнаружить только при выполнении программы.|
|[Класс underflow_error](../standard-library/underflow-error-class.md)|Этот класс служит базовым для всех исключений, создаваемых для сообщения об арифметической неточности.|

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
