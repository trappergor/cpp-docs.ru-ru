---
title: Класс контейнера::reference
ms.date: 11/04/2016
helpviewer_keywords:
- reference method
ms.assetid: ab85a9fb-c628-4761-9a5f-a0231fad7690
ms.openlocfilehash: ccd944e433e332ddd75f8a26e8db919c26d6e35b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453321"
---
# <a name="container-classreference"></a>Класс контейнера::reference

> [!NOTE]
> Этот раздел находится в документации Майкрософт C++ как нефункциональный пример контейнеров, C++ используемых в стандартной библиотеке. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Описывает объект, который можно использовать в качестве ссылки на элемент управляемой последовательности.

## <a name="syntax"></a>Синтаксис

```

typedef T2 reference;
```

## <a name="remarks"></a>Примечания

Он описан здесь как синоним для неопределенного типа `T2` (обычно `Alloc::reference`). Объект типа `reference` можно привести к объекту типа [const_reference](../standard-library/container-class-const-reference.md).

## <a name="see-also"></a>См. также

[Пример класса контейнера](../standard-library/sample-container-class.md)
