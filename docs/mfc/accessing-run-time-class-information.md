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
ms.openlocfilehash: a9f90640007f84c854d59cc27e0c38459c76fe46
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619201"
---
# <a name="accessing-run-time-class-information"></a>Доступ к сведениям о классе во время выполнения

В этой статье объясняется, как получить доступ к сведениям о классе объекта во время выполнения.

> [!NOTE]
> MFC не использует поддержку [сведений о типах во время выполнения](../cpp/run-time-type-information.md) (RTTI), введенную в Visual C++ 4,0.

Если ваш класс был производным от [CObject](reference/cobject-class.md) и использовал **объявления**_**dynamic** и `IMPLEMENT_DYNAMIC` , или, или, а также макросы и, `DECLARE_DYNCREATE` `IMPLEMENT_DYNCREATE` `DECLARE_SERIAL` `IMPLEMENT_SERIAL` описанные в статье [Создание производного класса от CObject](deriving-a-class-from-cobject.md), `CObject` класс может определить точный класс объекта во время выполнения.

Эта возможность наиболее полезна, если требуется проверка дополнительных типов аргументов функции, и если необходимо написать специальный код на основе класса объекта. Однако этот подход обычно не рекомендуется, так как он дублирует функциональные возможности виртуальных функций.

`CObject`Функцию-член `IsKindOf` можно использовать, чтобы определить, принадлежит ли определенный объект указанному классу или является ли он производным от конкретного класса. Аргумент для `IsKindOf` — это `CRuntimeClass` объект, который можно получить с помощью `RUNTIME_CLASS` макроса с именем класса.

### <a name="to-use-the-runtime_class-macro"></a>Использование макроса RUNTIME_CLASS

1. Используйте `RUNTIME_CLASS` с именем класса, как показано здесь для класса `CObject` :

   [!code-cpp[NVC_MFCCObjectSample#4](codesnippet/cpp/accessing-run-time-class-information_1.cpp)]

Вам редко приходится обращаться непосредственно к объекту класса времени выполнения. Чаще всего используется передача объекта класса времени выполнения в `IsKindOf` функцию, как показано в следующей процедуре. `IsKindOf`Функция проверяет, принадлежит ли объект определенному классу.

#### <a name="to-use-the-iskindof-function"></a>Использование функции IsKindOf

1. Убедитесь, что класс имеет поддержку класса времени выполнения. То есть класс должен быть производным напрямую или косвенно от `CObject` и использовал **объявления**_**dynamic** и,, `IMPLEMENT_DYNAMIC` или, а также `DECLARE_DYNCREATE` макросы и, `IMPLEMENT_DYNCREATE` `DECLARE_SERIAL` `IMPLEMENT_SERIAL` описанные в статье, [порожденной классом от CObject](deriving-a-class-from-cobject.md).

1. Вызовите `IsKindOf` функцию члена для объектов этого класса, используя `RUNTIME_CLASS` макрос для создания `CRuntimeClass` аргумента, как показано ниже:

   [!code-cpp[NVC_MFCCObjectSample#2](codesnippet/cpp/accessing-run-time-class-information_2.h)]

   [!code-cpp[NVC_MFCCObjectSample#5](codesnippet/cpp/accessing-run-time-class-information_3.cpp)]

    > [!NOTE]
    >  IsKindOf возвращает **значение true** , если объект является членом указанного класса или класса, производного от указанного класса. `IsKindOf`не поддерживает множественное наследование или виртуальные базовые классы, хотя при необходимости можно использовать множественное наследование для производных классов Microsoft Foundation.

Одним из использования сведений о классе времени выполнения является динамическое создание объектов. Этот процесс рассматривается в статье [Создание динамического объекта](dynamic-object-creation.md).

Более подробные сведения о сериализации и сведения о классах времени выполнения см. в [файлах статей в MFC](files-in-mfc.md) и [сериализации](serialization-in-mfc.md).

## <a name="see-also"></a>См. также раздел

[Использование CObject](using-cobject.md)
