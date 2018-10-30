---
title: 'Элементы ActiveX в MFC: Оптимизация | Документация Майкрософт'
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], windowless
- flicker-free ActiveX controls
- MFC ActiveX controls [MFC], mouse interaction
- device contexts, unclipped for MFC ActiveX controls
- MFC ActiveX controls [MFC], optimizing
- performance, ActiveX controls
- optimization, ActiveX controls
- MFC ActiveX controls [MFC], flicker-free
- windowless MFC ActiveX controls
- MFC ActiveX controls [MFC], active/inactive state
- optimizing performance, ActiveX controls
ms.assetid: 8b11f26a-190d-469b-b594-5336094a0109
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a583b0b70473698963841a3bd9c84c79472eb529
ms.sourcegitcommit: a3c9e7888b8f437a170327c4c175733ad9eb0454
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50204448"
---
# <a name="mfc-activex-controls-optimization"></a>Элементы управления ActiveX в MFC. Оптимизация

Здесь объясняются методы, которые можно использовать для оптимизации элементов управления ActiveX для повышения производительности.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, заменяющие ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).

Разделы [Включение отключение параметра "Активация при видимым"](../mfc/turning-off-the-activate-when-visible-option.md) и [предоставляя мыши взаимодействия во время неактивного](../mfc/providing-mouse-interaction-while-inactive.md) обсудить элементов управления, которые не создать окно до момента активации. Раздел [предоставление активации без окна](../mfc/providing-windowless-activation.md) рассматриваются элементы управления, которые никогда не создаст это окно, даже в том случае, если они активируются.

Windows имеют два основных недостатка для объектов OLE: они предотвратить объектов прозрачного или непрямоугольное в активном состоянии и добавляют большие издержки при создании и отображения элементов управления. Обычно при создании окна занимает 60 процентов времени создания элемента управления. С помощью одного общего окна (обычно контейнера) и диспетчеризации кода элемент управления получает те же службы окна, обычно без потери производительности. Наличие окна является главным образом ненужным издержкам для объекта.

Некоторые оптимизации не обязательно повысить производительность, когда элемент управления используется в некоторых контейнерах. Например контейнеры, выпущенным до 1996 не поддерживали активации без окна, реализация этой возможности не обеспечивает преимущество в более старых контейнеры. Тем не менее почти все контейнер поддерживает сохраняемости, поэтому оптимизация кода сохранения состояния элемента управления скорее всего, повысит производительность в любом контейнере. Если элемент управления, специально предназначенных для использования с одного определенного типа контейнера, можно проанализировать, какие из этих оптимизаций поддерживается в этом контейнере. Как правило тем не менее, рекомендуется реализовать так же, как многие из этих методов, как применяются к вашему элементу управления, чтобы убедиться, что элемент управления выполняет надлежащим образом, возможно в различные контейнеры.

Вы можете реализовать множество из этих оптимизаций через [мастер элементов управления ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md)на [параметры управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) страницы.

### <a name="mfc-activex-control-wizard-ole-optimization-options"></a>Элемент управления ActiveX мастер MFC OLE-параметров оптимизации

|Параметр управления в мастер элементов управления ActiveX MFC|Действие|Дополнительные сведения|
|-------------------------------------------------------|------------|----------------------|
|**Активация при отображении** "флажок"|Clear|[Отключение активации, когда отображается параметр](../mfc/turning-off-the-activate-when-visible-option.md)|
|**Активации без окна** "флажок"|Выбрать|[Предоставление активации без окна](../mfc/providing-windowless-activation.md)|
|**Необрезанного контекста устройства** "флажок"|Выбрать|[Использование необрезанного контекста устройства](../mfc/using-an-unclipped-device-context.md)|
|**Без мерцания активации** "флажок"|Выбрать|[Обеспечение активации без мерцания](../mfc/providing-flicker-free-activation.md)|
|**Мыши уведомления указателя мыши при неактивной** "флажок"|Выбрать|[Обеспечение взаимодействия с мышью в неактивном режиме](../mfc/providing-mouse-interaction-while-inactive.md)|
|**Оптимизированный код отрисовки** "флажок"|Выбрать|[Оптимизация рисования элементов управления](../mfc/optimizing-control-drawing.md)|

Подробные сведения о функциях-членах, которые реализуют эти оптимизации см. в разделе [COleControl](../mfc/reference/colecontrol-class.md).

Дополнительные сведения:

- [Оптимизация постоянства и инициализации](../mfc/optimizing-persistence-and-initialization.md)

- [Предоставление активации без окна](../mfc/providing-windowless-activation.md)

- [Отключение активации, когда отображается параметр](../mfc/turning-off-the-activate-when-visible-option.md)

- [Обеспечение взаимодействия с мышью в неактивном режиме](../mfc/providing-mouse-interaction-while-inactive.md)

- [Обеспечение активации без мерцания](../mfc/providing-flicker-free-activation.md)

- [Использование необрезанного контекста устройства](../mfc/using-an-unclipped-device-context.md)

- [Оптимизация рисования элементов управления](../mfc/optimizing-control-drawing.md)

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

