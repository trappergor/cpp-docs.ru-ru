---
title: Класс bad_exception | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- exception/std::bad_exception
dev_langs:
- C++
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41b30763f1382b7a12f68cd6a45b87960f623649
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="badexception-class"></a>Класс bad_exception

Этот класс описывает исключение, которое может быть вызвано из обработчика unexpected.

## <a name="syntax"></a>Синтаксис

```cpp
class bad_exception    : public exception {};
```

## <a name="remarks"></a>Примечания

Обработчик [unexpected](../standard-library/exception-functions.md#unexpected) вызовет `bad_exception` вместо завершения или вместо вызова другой функции, указанной с помощью [set_unexpected](../standard-library/exception-functions.md#set_unexpected), если `bad_exception` включен в список throw функции.

Значение, возвращаемое **what**, — это определяемая в реализации строка C. Ни одна из функций-членов не создает исключение.

Список членов, наследуемых классом `bad_exception`, см. в разделе [Класс exception](../standard-library/exception-class.md).

## <a name="example"></a>Пример

Пример использования [unexpected](../standard-library/exception-functions.md#unexpected), вызывающего `bad_exception`, см. в разделе [set_unexpected](../standard-library/exception-functions.md#set_unexpected).

## <a name="requirements"></a>Требования

**Заголовок:** \<exception>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Класс exception](../standard-library/exception-class.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
