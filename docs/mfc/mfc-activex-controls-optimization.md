---
title: 'Элементы управления ActiveX MFC: Оптимизация | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: c91f147637b53250f8d373af9950d6205c82d3e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-optimization"></a>Элементы управления ActiveX в MFC. Оптимизация
В этой статье описываются методы, которые можно использовать для оптимизации элементов управления ActiveX для повышения производительности.  
  
 Разделы [включения Off "Активация при отображении"](../mfc/turning-off-the-activate-when-visible-option.md) и [предоставление мыши взаимодействия при неактивные](../mfc/providing-mouse-interaction-while-inactive.md) обсудить элементов управления, которые не создать окно до активации. Раздел [предоставление активации без окна](../mfc/providing-windowless-activation.md) рассматриваются элементы управления, которые никогда не создавать окно, даже в том случае, если они активируются.  
  
 Windows существует два основных недостатка для объектов OLE: они препятствует объекты прозрачным или непрямоугольного, когда активны, и они добавляют больших издержек при создании и отображения элементов управления. Как правило Создание окна занимает 60 процентов времени создания элемента управления. С одного общего окна (обычно контейнера) и кодом диспетчеризации элемент управления получает те же службы окна, как правило, без потери производительности. Наличие окна является главным образом ненужных затрат ресурсов для объекта.  
  
 Некоторые оптимизации не обязательно повысить производительность, когда элемент управления используется в некоторые контейнеры. Например контейнеры, выпущенные до 1996 не поддерживали активации без окна, реализации этой функции не дает преимуществ в более старых контейнеров. Тем не менее практически во всех контейнер поддерживает сохраняемости, поэтому оптимизации кода элемента управления сохраняемости скорее всего повышает производительность в какой-либо контейнер. Если элемент управления специально предназначены для использования с одного определенного типа контейнера, можно проанализировать, какие из этих оптимизаций поддерживается в этом контейнере. Как правило тем не менее, следует реализовать как многие из этих методов, применимых в определенный элемент управления, чтобы убедиться, что элемент управления выполняет надлежащим образом, возможно, можно в самых разных контейнеров.  
  
 Можно реализовать многие из этих оптимизаций через [мастер элементов управления ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md)на [параметры управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) страницы.  
  
### <a name="mfc-activex-control-wizard-ole-optimization-options"></a>Параметры оптимизации OLE мастер элементов управления ActiveX MFC  
  
|Параметр управления в мастер элементов управления ActiveX MFC|Действие|Дополнительные сведения|  
|-------------------------------------------------------|------------|----------------------|  
|**Активация при отображении** флажок|Clear|[Отключение активации, когда отображается параметр](../mfc/turning-off-the-activate-when-visible-option.md)|  
|**Активации без окна** флажок|Выбрать|[Предоставление активации без окна](../mfc/providing-windowless-activation.md)|  
|**Необрезанный контекст устройства** флажок|Выбрать|[Использование необрезанного контекста устройства](../mfc/using-an-unclipped-device-context.md)|  
|**Без мерцания активации** флажок|Выбрать|[Обеспечение активации без мерцания](../mfc/providing-flicker-free-activation.md)|  
|**Указатель мыши находится указатель уведомления неактивная** флажок|Выбрать|[Обеспечение взаимодействия с мышью в неактивном режиме](../mfc/providing-mouse-interaction-while-inactive.md)|  
|**Оптимизированный код отрисовки** флажок|Выбрать|[Оптимизация рисования элементов управления](../mfc/optimizing-control-drawing.md)|  
  
 Дополнительные сведения о функции-члены, реализующие эти оптимизации см. в разделе [COleControl](../mfc/reference/colecontrol-class.md). Функции-члены перечисляются по использования, такие как [без окон операции](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df) и [функции обработки неактивные указатель](http://msdn.microsoft.com/en-us/e9e28f79-9a70-4ae4-a5aa-b3e92f1904df).  
  
 Дополнительные сведения:  
  
-   [Оптимизация постоянства и инициализации](../mfc/optimizing-persistence-and-initialization.md)  
  
-   [Предоставление активации без окна](../mfc/providing-windowless-activation.md)  
  
-   [Отключение активации, когда отображается параметр](../mfc/turning-off-the-activate-when-visible-option.md)  
  
-   [Обеспечение взаимодействия с мышью в неактивном режиме](../mfc/providing-mouse-interaction-while-inactive.md)  
  
-   [Обеспечение активации без мерцания](../mfc/providing-flicker-free-activation.md)  
  
-   [Использование необрезанного контекста устройства](../mfc/using-an-unclipped-device-context.md)  
  
-   [Оптимизация рисования элементов управления](../mfc/optimizing-control-drawing.md)  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

