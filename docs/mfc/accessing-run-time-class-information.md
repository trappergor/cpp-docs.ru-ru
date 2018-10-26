---
title: Доступ к сведениям о классе среды выполнения | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], and RTTI
- CObject class [MFC], using IsKindOf method [MFC]
- run time [MFC], class information
- RUNTIME_CLASS macro [MFC]
- CObject class [MFC], using RUNTIME_CLASS macro [MFC]
- RTTI compiler option [MFC]
- CObject class [MFC], accessing run-time class information
- run time [MFC]
- IsKindOf method method [MFC]
- run-time class [MFC], accessing information
- classes [MFC], run-time class information
- run-time class [MFC]
- RUNTIME_CLASS macro, using
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61da17093d56dcfd8b0eeec3ade7955f27bc6b85
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50077722"
---
# <a name="accessing-run-time-class-information"></a>Доступ к сведениям о классе во время выполнения

В этой статье объясняется, как для доступа к сведениям о классе объекта во время выполнения.

> [!NOTE]
>  Не использует MFC [сведения о типе времени выполнения](../cpp/run-time-type-information.md) поддержки (RTTI), появившихся в Visual C++ 4.0.

Производного от класса [CObject](../mfc/reference/cobject-class.md) и использовать **DECLARE**_**динамическое** и `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` и `IMPLEMENT_DYNCREATE`, или `DECLARE_SERIAL` и `IMPLEMENT_SERIAL` макросы описано в статье [наследование класса от CObject](../mfc/deriving-a-class-from-cobject.md), `CObject` класс имеет возможность определить точный класс объекта, который во время выполнения.

Эта возможность наиболее полезна в случаях, когда требуется дополнительного типа, проверяющего аргументов функции и когда необходимо написать специальный код, на основе класса объекта. Тем не менее это не рекомендуется обычно так, как она дублирует функциональные возможности виртуальных функций.

`CObject` Функция-член `IsKindOf` может использоваться для определения, если определенный объект принадлежит к указанному классу или если он является производным от определенного класса. Аргумент `IsKindOf` — `CRuntimeClass` объект, который можно получить с помощью `RUNTIME_CLASS` макрос с именем класса.

### <a name="to-use-the-runtimeclass-macro"></a>Использование макроса RUNTIME_CLASS

1. Используйте `RUNTIME_CLASS` с именем класса, как показано ниже, для класса `CObject`:

   [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]

Редко требуется прямой доступ к объекте класса среды выполнения. Более обычно используется для передачи объекта класс времени выполнения для `IsKindOf` функции, как показано в следующей процедуре. `IsKindOf` Функция проверяет объект принадлежит ли он для определенного класса.

#### <a name="to-use-the-iskindof-function"></a>Чтобы использовать функцию IsKindOf

1. Убедитесь, что у класса имеется поддержка класс времени выполнения. То есть класс должен полученных прямо или косвенно из `CObject` и использовать **DECLARE**_**динамическое** и `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` и `IMPLEMENT_DYNCREATE`, или `DECLARE_SERIAL` и `IMPLEMENT_SERIAL` макросы описано в статье [наследование класса от CObject](../mfc/deriving-a-class-from-cobject.md).

1. Вызовите `IsKindOf` функция-член для объектов этого класса, с помощью `RUNTIME_CLASS` макрос для создания `CRuntimeClass` аргумент, как показано ниже:

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]

   [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]

    > [!NOTE]
    >  Возвращает IsKindOf **TRUE** Если объект является членом указанного класса или класса, производного от указанного класса. `IsKindOf` не поддерживает множественные наследования или виртуальными базовыми классами, несмотря на то, что при необходимости можно использовать множественное наследование для производных классов Microsoft Foundation.

Сведения о классе среды выполнения применяется в динамическое создание объектов. Этот процесс описывается в статье [динамического создания объектов](../mfc/dynamic-object-creation.md).

Дополнительные сведения о сериализации и сведения о классе среды выполнения, см. в статьях [файлы в MFC](../mfc/files-in-mfc.md) и [сериализации](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>См. также

[Использование CObject](../mfc/using-cobject.md)

