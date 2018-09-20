---
title: 'Элементы ActiveX в MFC: Доступ к свойствам окружения | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], accessing ambient properties
- properties [MFC], accessing ambient
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8aaa379513695f3cd39589a1009e3a157d957761
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407916"
---
# <a name="mfc-activex-controls-accessing-ambient-properties"></a>Элементы управления ActiveX в MFC. Доступ к свойствам окружения

В этой статье рассматривается, как элемент управления ActiveX можно доступа к свойствам окружения контейнера элемента управления.

Элемент управления можно получить сведения о его контейнера, доступ к свойствам окружения контейнера. Эти свойства предоставляют визуальные характеристики, такие как цвет фона контейнера, текущий шрифт, используемый контейнера и рабочие характеристики, такие как ли контейнер в настоящее время находится в пользовательском режиме или в режим конструктора. Элемент управления может использовать внешние свойства для настройки внешнего вида и поведения для конкретного контейнера, в котором он внедрен. Тем не менее элемент управления предполагать, что поддерживает любой конкретной внешнее свойство контейнера. На самом деле некоторые контейнеры могут не поддерживать все внешние свойства вообще. При отсутствии внешнее свойство элемент управления должен принимать значение разумного значения по умолчанию.

Для доступа к внешним, сделать вызов к [COleControl::GetAmbientProperty](../mfc/reference/colecontrol-class.md#getambientproperty). Эта функция ожидает идентификатор диспетчеризации внешнее свойство в качестве первого параметра (файл OLECTL. H определяет диспетчерские идентификаторы для стандартного набора свойства окружающей среды).

Параметры `GetAmbientProperty` функции являются идентификатор диспетчеризации, тег variant, указывающее, ожидаемый тип свойства и указатель на область памяти, где должно возвращаться значение. Тип данных, к которому относится этот указатель будет зависеть от variant тега. Функция возвращает **TRUE** Если контейнер поддерживает свойство, в противном случае возвращается **FALSE**.

В следующем примере кода получает значение внешнего свойства, называется «Освобождение». Если свойство не поддерживается в качестве контейнера, значение по умолчанию **TRUE** предполагается, что:

[!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/cpp/mfc-activex-controls-accessing-ambient-properties_1.cpp)]

Для удобства `COleControl` предоставляет вспомогательные функции, которые доступ ко многим часто используемые свойства окружающей среды и возвращать значения по умолчанию, если свойства недоступны. Ниже приведены эти вспомогательные функции.

- [COleControl::AmbientBackColor](../mfc/reference/colecontrol-class.md#ambientbackcolor)

- [AmbientDisplayName](../mfc/reference/colecontrol-class.md#ambientdisplayname)

- [AmbientFont](../mfc/reference/colecontrol-class.md#ambientfont)

    > [!NOTE]
    >  Вызывающий объект должен вызвать метод `Release( )` от возвращенного шрифта.

- [AmbientForeColor](../mfc/reference/colecontrol-class.md#ambientforecolor)

- [AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid)

- [AmbientScaleUnits](../mfc/reference/colecontrol-class.md#ambientscaleunits)

- [AmbientTextAlign](../mfc/reference/colecontrol-class.md#ambienttextalign)

- [AmbientUserMode](../mfc/reference/colecontrol-class.md#ambientusermode)

- [AmbientUIDead](../mfc/reference/colecontrol-class.md#ambientuidead)

- [AmbientShowHatching](../mfc/reference/colecontrol-class.md#ambientshowhatching)

- [AmbientShowGrabHandles](../mfc/reference/colecontrol-class.md#ambientshowgrabhandles)

При изменении значения свойства окружающей среды (через какое-либо действие контейнера) `OnAmbientPropertyChanged` вызовом функции-члена элемента управления. Переопределите эта функция-член для обработки такого уведомления. Параметр для `OnAmbientPropertyChanged` идентификатор диспетчеризации затронутых внешнее свойство. Значение этот идентификатор диспетчеризации может быть DISPID_UNKNOWN, который указывает, что изменилось одно или несколько свойств окружения, но сведения о том, какие свойства были затронуты являются недоступными.

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

