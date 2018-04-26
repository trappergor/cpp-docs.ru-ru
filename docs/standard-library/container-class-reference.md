---
title: Класс контейнера::reference | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- reference method
ms.assetid: ab85a9fb-c628-4761-9a5f-a0231fad7690
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca6cfbd219f8184194e155c4223453ed510ba6a5
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
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

Он описан здесь как синоним для неопределенного типа **T2** (обычно **Alloc::reference**). Объект типа **reference** может быть приведен к объекту типа [const_reference](../standard-library/container-class-const-reference.md).

## <a name="see-also"></a>См. также

[Пример класса контейнера](../standard-library/sample-container-class.md)<br/>
