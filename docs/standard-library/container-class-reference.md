---
title: Класс контейнера::reference | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- reference method
ms.assetid: ab85a9fb-c628-4761-9a5f-a0231fad7690
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13883e1426be22c8cf3d329be33258c69511900d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966023"
---
# <a name="container-classreference"></a>Класс контейнера::reference

> [!NOTE]
> Данный раздел включен в документацию Visual C++ в качестве нефункционального примера контейнеров, используемых в стандартной библиотеке C++. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Описывает объект, который можно использовать в качестве ссылки на элемент управляемой последовательности.

## <a name="syntax"></a>Синтаксис

```

typedef T2 reference;
```

## <a name="remarks"></a>Примечания

Он описан здесь как синоним для неопределенного типа `T2` (обычно `Alloc::reference`). Объект типа `reference` может быть приведен к объекту типа [const_reference](../standard-library/container-class-const-reference.md).

## <a name="see-also"></a>См. также

[Пример класса контейнера](../standard-library/sample-container-class.md)<br/>
