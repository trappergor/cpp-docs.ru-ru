---
title: Динамическое создание объектов
ms.date: 03/27/2020
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
ms.openlocfilehash: 40a17d3ed458d0634fd5bf27b54d0a36a65e35b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364809"
---
# <a name="dynamic-object-creation"></a>Динамическое создание объектов

В этой статье объясняется, как динамически создать объект во время выполнения. Процедура использует информацию о классе времени выполнения, о чем говорится в статье [Доступ к информации о run-Time Class.](../mfc/accessing-run-time-class-information.md)

#### <a name="dynamically-create-an-object-given-its-run-time-class"></a>Динамически создать объект с учетом его класса времени выполнения

1. Используйте следующий код для динамического `CreateObject` создания `CRuntimeClass`объекта с использованием функции . При сбое возвращается `CreateObject` **NULL** вместо того, чтобы поднимать исключение:

   [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>См. также раздел

[Уничтожение оконных объектов](tn017-destroying-window-objects.md)
[с помощью CObject](using-cobject.md)
