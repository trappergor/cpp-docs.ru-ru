---
title: Класс контейнера::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 11e13fc74de779076b40ba338a21a6736eb04e06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62211060"
---
# <a name="container-classerase"></a>Класс контейнера::erase

> [!NOTE]
> Данный раздел включен в документацию Visual C++ в качестве нефункционального примера контейнеров, используемых в стандартной библиотеке C++. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

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
