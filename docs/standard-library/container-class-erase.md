---
title: Класс контейнера::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 0ef4db1c14942fc896f10095ff2331648d27c820
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221637"
---
# <a name="container-classerase"></a>Класс контейнера::erase

> [!NOTE]
> Этот раздел находится в Microsoft C++ документации в качестве нефункционального примера контейнеров, используемых в C++ стандартной библиотеки. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Удаляет элемент.

## <a name="syntax"></a>Синтаксис

```

    iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>Примечания

Первая функция-член удаляет элемент управляемой последовательности, на которые указывают *_Where*. Вторая функция-член удаляет элементы управляемой последовательности в диапазоне [`first`, `last`). Обе возвращают итератор, который обозначает первый элемент, находящийся за всеми удаленными элементами, или [end](../standard-library/container-class-end.md), если такой элемент не существует.

Функции-члены вызывают исключение только в том случае, если операция копирования создает исключение.

## <a name="see-also"></a>См. также

[Пример класса контейнера](../standard-library/sample-container-class.md)<br/>
