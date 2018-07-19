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
ms.openlocfilehash: b3813fae7a9ae6105d4a3dfe4e72ac1773a10e65
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954660"
---
# <a name="badexception-class"></a>Класс bad_exception

Этот класс описывает исключение, которое может быть вызвано из обработчика unexpected.

## <a name="syntax"></a>Синтаксис

```cpp
class bad_exception    : public exception {};
```

## <a name="remarks"></a>Примечания

Обработчик [unexpected](../standard-library/exception-functions.md#unexpected) вызовет `bad_exception` вместо завершения или вместо вызова другой функции, указанной с помощью [set_unexpected](../standard-library/exception-functions.md#set_unexpected), если `bad_exception` включен в список throw функции.

Значение, возвращенное `what` является строка C определяемого реализацией. Ни одна из функций-членов не создает исключение.

Список членов, наследуемых классом `bad_exception`, см. в разделе [Класс exception](../standard-library/exception-class.md).

## <a name="example"></a>Пример

Пример использования [unexpected](../standard-library/exception-functions.md#unexpected), вызывающего `bad_exception`, см. в разделе [set_unexpected](../standard-library/exception-functions.md#set_unexpected).

## <a name="requirements"></a>Требования

**Заголовок:** \<exception>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Класс exception](../standard-library/exception-class.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
