---
title: Доступ к сведениям о классе во время выполнения
ms.date: 11/04/2016
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
ms.openlocfilehash: 4a836bb7bd03bd6654e5c940442fecf541042fd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354229"
---
# <a name="accessing-run-time-class-information"></a>Доступ к сведениям о классе во время выполнения

В этой статье объясняется, как получить доступ к информации о классе объекта во время выполнения.

> [!NOTE]
> MFC не использует поддержку [Run-Time Type Information](../cpp/run-time-type-information.md) (RTTI), введенную в Visual C'4.0.

Если вы вывели свой класс из [CObject](../mfc/reference/cobject-class.md) и `IMPLEMENT_DYNAMIC`использовали `DECLARE_DYNCREATE` `IMPLEMENT_DYNCREATE` **DECLARE**- `DECLARE_SERIAL` `IMPLEMENT_SERIAL` **DYNAMIC** и , и , или и макросы объяснил в статье [Вывод класса от CObject](../mfc/deriving-a-class-from-cobject.md), `CObject` класс имеет возможность определить точный класс объекта во время выполнения.

Эта способность наиболее полезна, когда требуется дополнительная проверка типов функциональных аргументов и когда необходимо написать специальный код на основе класса объекта. Однако эта практика обычно не рекомендуется, поскольку она дублирует функциональность виртуальных функций.

Функция `CObject` `IsKindOf` члена может быть использована для определения того или иного объекта к определенному классу или же он получен из определенного класса. Аргументом `IsKindOf` `CRuntimeClass` является объект, который можно получить `RUNTIME_CLASS` с помощью макроса с названием класса.

### <a name="to-use-the-runtime_class-macro"></a>Использовать RUNTIME_CLASS макрос

1. Используйте `RUNTIME_CLASS` с названием класса, как показано `CObject`здесь для класса:

   [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]

Редко вам будет нужен доступ к объекту класса времени выполнения напрямую. Более распространенным использованием является передача объекта класса `IsKindOf` времени выполнения функции, как показано в следующей процедуре. Функция `IsKindOf` проверяет объект, чтобы увидеть, принадлежит ли он определенному классу.

#### <a name="to-use-the-iskindof-function"></a>Использовать функцию IsKindOf

1. Убедитесь, что класс имеет поддержку класса времени выполнения. То есть, класс должен быть получен прямо `CObject` или косвенно из и `IMPLEMENT_DYNAMIC`используется `DECLARE_DYNCREATE` `IMPLEMENT_DYNCREATE` **DECLARE**- `DECLARE_SERIAL` `IMPLEMENT_SERIAL` **DYNAMIC** и , и , или и макросов, объяснил в статье [Вывод класса от CObject](../mfc/deriving-a-class-from-cobject.md).

1. Вызов `IsKindOf` функции участника для объектов `RUNTIME_CLASS` этого класса, `CRuntimeClass` используя макрос для создания аргумента, как показано здесь:

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]

   [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]

    > [!NOTE]
    >  IsKindOf возвращает **TRUE,** если объект является членом указанного класса или класса, полученного из указанного класса. `IsKindOf`не поддерживает несколько классов наследования или виртуальных базовых классов, хотя при необходимости можно использовать несколько наследований для полученных классов Фонда Майкрософт.

Одно из видов использования информации о классе времени выполнения — в динамическом создании объектов. Этот процесс обсуждается в статье [Dynamic Object Creation](../mfc/dynamic-object-creation.md).

Для получения более подробной информации о сериализации и время выполнения [Serialization](../mfc/serialization-in-mfc.md)класса информации, [см.](../mfc/files-in-mfc.md)

## <a name="see-also"></a>См. также раздел

[Использование CObject](../mfc/using-cobject.md)
