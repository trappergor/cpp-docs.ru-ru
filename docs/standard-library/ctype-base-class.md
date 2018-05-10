---
title: Класс ctype_base | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- locale/std::ctype_base
dev_langs:
- C++
helpviewer_keywords:
- ctype_base class
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3def685a8cd108666b3e1b8be9314fc7585a9837
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="ctypebase-class"></a>Класс ctype_base

Этот класс служит в качестве базового класса для аспектов класса шаблона [ctype](../standard-library/ctype-class.md). Базовый класс для класса ctype, используемый для определения типов перечисления, применяемых для классификации или тестирования символов по отдельности или целыми диапазонами.

## <a name="syntax"></a>Синтаксис

```cpp
struct ctype_base : public locale::facet
{
    enum
    {
        alnum,
        alpha,
        cntrl,
        digit,
        graph,
        lower,
        print,
        punct,
        space,
        upper,
        xdigit
    };
    typedef short mask;

    ctype_base( size_t _Refs = 0 );
    ~ctype_base();
};
```

## <a name="remarks"></a>Примечания

Задает маску перечисления. Каждая константа перечисления характеризует другой способ классификации символов, в соответствии с определениями функций с подобными именами, объявленных в заголовке \<ctype.h>. Используются следующие константы:

- **space** (функция [isspace](../standard-library/locale-functions.md#isspace))

- **print** (функция [isprint](../standard-library/locale-functions.md#isprint))

- **cntrl** (функция [iscntrl](../standard-library/locale-functions.md#iscntrl))

- **upper** (функция [isupper](../standard-library/locale-functions.md#isupper))

- **lower** (функция [islower](../standard-library/locale-functions.md#islower))

- **digit** (функция [isdigit](../standard-library/locale-functions.md#isdigit))

- **punct** (функция [ispunct](../standard-library/locale-functions.md#ispunct))

- **xdigit** (функция [isxdigit](../standard-library/locale-functions.md#isxdigit))

- **alpha** (функция [isalpha](../standard-library/locale-functions.md#isalpha))

- **alnum** (функция [isalnum](../standard-library/locale-functions.md#isalnum))

- **graph** (функция [isgraph](../standard-library/locale-functions.md#isgraph))

Вы можете охарактеризовать комбинацию классификаций, выполняя операцию OR с этими константами. В частности, это всегда имеет значение true, **alnum** == ( **альфа-канал** &#124; **цифра** \) и **graph** \= \= \( **alnum** &#124; **пунктуация**).

## <a name="requirements"></a>Требования

**Заголовок:** \<locale>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
