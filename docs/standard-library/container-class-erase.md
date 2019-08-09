---
title: Класс контейнера::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 1463a854c314884f0b3b6bffa5d37dfb7fec4a6f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454514"
---
# <a name="container-classerase"></a>Класс контейнера::erase

> [!NOTE]
> Этот раздел находится в документации Майкрософт C++ как нефункциональный пример контейнеров, C++ используемых в стандартной библиотеке. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

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

Первая функция члена удаляет элемент управляемой последовательности, на которую указывает *_Where*. Вторая функция-член удаляет элементы управляемой последовательности в диапазоне [`first`, `last`). Обе возвращают итератор, который обозначает первый элемент, находящийся за всеми удаленными элементами, или [end](../standard-library/container-class-end.md), если такой элемент не существует.

Функции-члены вызывают исключение только в том случае, если операция копирования создает исключение.

## <a name="see-also"></a>См. также

[Пример класса контейнера](../standard-library/sample-container-class.md)
