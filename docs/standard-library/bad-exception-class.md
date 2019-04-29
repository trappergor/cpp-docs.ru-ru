---
title: Класс bad_exception
ms.date: 11/04/2016
f1_keywords:
- exception/std::bad_exception
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 94d1104b66fc6bd84e209caa23ce309cffd9fa85
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377830"
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
