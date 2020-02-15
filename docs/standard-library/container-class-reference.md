---
title: Класс контейнера::reference
ms.date: 11/04/2016
helpviewer_keywords:
- reference method
ms.assetid: ab85a9fb-c628-4761-9a5f-a0231fad7690
ms.openlocfilehash: a9a28b37f8fa175d5768b215f5eca5183d31708b
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257875"
---
# <a name="container-classreference"></a>Класс контейнера::reference

> [!NOTE]
> Этот раздел находится в документации Майкрософт C++ как нефункциональный пример контейнеров, C++ используемых в стандартной библиотеке. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Описывает объект, который можно использовать в качестве ссылки на элемент управляемой последовательности.

## <a name="syntax"></a>Синтаксис

```cpp
typedef T2 reference;
```

## <a name="remarks"></a>Примечания

Он описан здесь как синоним для неопределенного типа `T2` (обычно `Alloc::reference`). Объект типа `reference` может быть приведен к объекту типа [const_reference](../standard-library/container-class-const-reference.md).

## <a name="see-also"></a>См. также:

[Пример класса контейнера](../standard-library/sample-container-class.md)
