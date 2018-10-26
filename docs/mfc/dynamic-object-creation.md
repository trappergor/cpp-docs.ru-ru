---
title: Динамическое создание объектов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1b8cca1453ef4a044a39853e615c5d0e6c3268f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50051893"
---
# <a name="dynamic-object-creation"></a>Динамическое создание объектов

В этой статье объясняется, как создать объект динамически во время выполнения. В процедуре используются сведения о классе среды выполнения, как описано в статье [доступ к сведениям о классе среды выполнения](../mfc/accessing-run-time-class-information.md).

#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>Для динамического создания объекта, заданного его класс времени выполнения

1. Используйте указанный ниже код для динамического создания объекта с помощью `CreateObject` функции `CRuntimeClass`. Обратите внимание, что в случае сбоя `CreateObject` возвращает **NULL** вместо активизации исключения:

   [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]

## <a name="see-also"></a>См. также

[Использование CObject](../mfc/using-cobject.md)

