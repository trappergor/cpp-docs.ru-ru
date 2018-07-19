---
title: Структура char_traits&lt;wchar_t&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- char_traits<wchar_t>
- iosfwd/std::char_traits<wchar_t>
dev_langs:
- C++
helpviewer_keywords:
- char_traits<wchar_t> class
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7d8b87b51bfeef68ef8bfe22c8e7e201929aa3f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957078"
---
# <a name="chartraitsltwchartgt-struct"></a>Структура char_traits&lt;wchar_t&gt;

Класс, который является специализацией структуры шаблона **char_traits\<CharType >** на элемент типа **wchar_t**.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
struct char_traits<wchar_t>;
```

## <a name="remarks"></a>Примечания

Специализация позволяет структуре использовать преимущества библиотечных функций, манипулирующих объектами данного типа **wchar_t**.

## <a name="requirements"></a>Требования

**Заголовок:** \<string>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Структура char_traits](../standard-library/char-traits-struct.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
