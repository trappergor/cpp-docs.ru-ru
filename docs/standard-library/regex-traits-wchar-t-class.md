---
title: Класс regex_traits&lt;wchar_t&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- regex/std::regex_traits<wchar_t>
dev_langs:
- C++
helpviewer_keywords:
- regex_traits<wchar_t> class
ms.assetid: 288d6fdb-fb8e-4a4d-904a-53916be7f95b
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 19403ce75bd453754617167b2d6a26cc0a8deec8
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="regextraitsltwchartgt-class"></a>Класс regex_traits&lt;wchar_t&gt;

Специализация regex_traits для wchar_t.

## <a name="syntax"></a>Синтаксис

```cpp
template <>
class regex_traits<wchar_t>
```

## <a name="remarks"></a>Примечания

Этот класс является явной специализацией шаблона класса [regex_traits](../standard-library/regex-traits-class.md) для элементов типа `wchar_t` (благодаря этому он может использовать преимущества библиотечных функций, манипулирующих объектами данного типа).

## <a name="requirements"></a>Требования

**Заголовок:** \<regex>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[\<regex>](../standard-library/regex.md)<br/>
[Класс regex_constants](../standard-library/regex-constants-class.md)<br/>
[Класс regex_error](../standard-library/regex-error-class.md)<br/>
[Функции \<regex>](../standard-library/regex-functions.md)<br/>
[Класс regex_iterator](../standard-library/regex-iterator-class.md)<br/>
[Операторы \<regex>](../standard-library/regex-operators.md)<br/>
[Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)<br/>
[Класс regex_traits](../standard-library/regex-traits-class.md)<br/>
[Определения типов \<regex>](../standard-library/regex-typedefs.md)<br/>
