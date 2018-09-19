---
title: Контейнеры элементов управления ATL часто задаваемые вопросы | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
- ATL, hosting ActiveX controls
- ActiveX controls [C++], hosting
- controls [ATL]
ms.assetid: d4bdfbe0-82ca-4f2f-bb95-cb89bdcc9b53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28e22df4eba5a12806221beea1966d1c1cdeae46
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052923"
---
# <a name="atl-control-containment-faq"></a>Часто задаваемые вопросы о вложении элементов управления ATL

## <a name="which-atl-classes-facilitate-activex-control-containment"></a>Какие классы ATL упрощают вложение элементов ActiveX?

Код размещения элементов управления ATL не требуется использовать любые классы ATL; можно просто создать **«AtlAxWin80»** окна и использование API размещения элементов управления, при необходимости (Дополнительные сведения см. в разделе **что такое API размещения элементов управления ATL**. Тем не менее следующие классы вам функциями вложения, проще использовать.

|Класс|Описание|
|-----------|-----------------|
|[CAxWindow](../atl/reference/caxwindow-class.md)|Заключает в оболочку **«AtlAxWin80»** окна, предоставлять методы для создания окна, создание элемента управления и/или присоединение элемент управления в окно и получение указателя на интерфейс объекта узла.|
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|Заключает в оболочку **«AtlAxWinLic80»** окно, в определении методов для создания окна, создание элемента управления и/или присоединение лицензированный элемент управления в окно и получение указателя на интерфейс объекта узла.|
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|Действует как базовый класс для классов элементов управления ActiveX, на основе ресурса диалогового окна. Такие элементы управления могут содержать другие элементы управления ActiveX.|
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|Действует как базовый класс для классов диалоговых окон, на основе ресурса диалогового окна. Такие диалоговые окна может содержать элементы управления ActiveX.|
|[CWindow](../atl/reference/cwindow-class.md)|Предоставляет метод, [GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol), возвращает указатель интерфейса на элемент управления, идентификатор окна ее размещения. Кроме того, программы-оболочки Windows API, предоставляемые `CWindow` обычно упростить управление окнами.|  

## <a name="what-is-the-atl-control-hosting-api"></a>Что такое ATL размещения элементов управления API?

ATL, размещение элементов управления API — это набор функций, позволяющий любое окно в качестве контейнера элементов управления ActiveX. Эти функции могут быть статически или динамически связанной в проект, так как они были доступны в виде исходного кода и предоставляемые ATL90.dll. Функции размещения элементов управления, перечислены в следующей таблице.

|Функция|Описание|
|--------------|-----------------|
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|Создает объект главного приложения, подключает его к предоставленным окна, а затем присоединяет существующего элемента управления.|
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|Создает объект главного приложения, подключает его к предоставленным окна, а затем загружает в элемент управления.|
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает его в указанном окне, аналогичную [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol).|
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|Создает объект главного приложения, подключает его к предоставленным окна, а затем загружает в элемент управления (также позволяет настроить приемники событий).|
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает его в указанном окне, аналогичную [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic).|
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|Создает немодальное диалоговое окно из ресурса диалогового окна и возвращает дескриптор окна.|
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|Создает модальное диалоговое окно из ресурса диалогового окна.|
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|Возвращает **IUnknown** указатель интерфейса элемента управления, размещенного в окне.|
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|Возвращает **IUnknown** указатель на интерфейс объекта узла подключен к окну.|
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|Инициализирует код размещения элементов управления.|
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|Отменяет инициализацию кода размещения элементов управления.|

`HWND` Параметры в первых трех функций должны быть существующее окно (почти) любого типа. При вызове любого из этих трех функций явно (как правило, не придется), не передается дескриптор окна, уже выступает в качестве узла (если в таком случае существующий объект узла не будет освобожден).

Первые семь функции вызывают [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) неявно.

> [!NOTE]
>  API размещения элементов управления является основой поддержки ATL в контейнеры элементов управления ActiveX. Тем не менее обычно есть практически не требуется, чтобы вызывать эти функции напрямую в том случае, если воспользоваться преимуществами или наиболее эффективно использовать классы-оболочки ATL. Дополнительные сведения см. в разделе [которого классы упрощают ActiveX вложении элементов управления ATL](which-atl-classes-facilitate-activex-control-containment-q.md).  

## <a name="what-is-atlaxwin100"></a>Что такое AtlAxWin100?

`AtlAxWin100` — Это имя класса окна, чтобы обеспечить функциональные возможности размещения элементов управления ATL. При создании экземпляра этого класса, процедура окна автоматически будет использовать API размещения элементов управления для создания объекта узла, связанный с окном и загрузить его с элементом управления, указанный как заголовок окна. 

## <a name="when-do-i-need-to-call-atlaxwininit"></a>Когда нужно вызывать AtlAxWinInit?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) регистрирует **«AtlAxWin80»** класса окна (а также пару пользовательских сообщений окна), поэтому эту функцию необходимо вызывать перед попыткой создания главного окна. Тем не менее, не всегда нужно явно вызывать эту функцию с момента размещение API-интерфейсы (и классы, которые их используют) часто вызывайте эту функцию для вас. Нет никакого вреда от вызова этой функции более одного раза.

## <a name="what-is-a-host-object"></a>Что такое объект узла?

Объект узла является COM-объект, представляющий контейнер элементов управления ActiveX, предоставляемых ATL для конкретного окна. Узел объекта подклассы окна контейнера, чтобы она может отражать сообщений для элемента управления, он предоставляет интерфейсы контейнера, необходимые для использования элементом управления, а также предоставляет [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) и [ IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) интерфейсы, которые позволяют настроить среду элемента управления.

Объект узла можно использовать для задания свойства окружения контейнера.

## <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Можно разместить несколько элементов управления в одном окне?

Не поддерживается для размещения более одного элемента управления в одном окне ATL узла. Каждое окно узла предназначен для хранения ровно один элемент управления за раз (Это позволяет простой механизм для обработки сообщения отражение и на уровне элемента управления внешние свойства). Тем не менее если требуется, чтобы пользователю видеть несколько элементов управления в одном окне, это просто создавать несколько окон узла как дочерние элементы этого окна.

## <a name="can-i-reuse-a-host-window"></a>Можно ли повторно использовать основное окно?

Не рекомендуется повторно использовать узла windows. Чтобы обеспечить надежность кода, следует привязать срок существования вашего главного окна времени существования одного элемента управления.

## <a name="when-do-i-need-to-call-atlaxwinterm"></a>Когда нужно вызывать AtlAxWinTerm?

[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) отменяет регистрацию **«AtlAxWin80»** класс окна. Эту функцию следует вызывать (если больше не требуется для создания узла windows), после всех существующих окон узла будут уничтожены. Если вы не вызываете эту функцию, класс окна будет отменена автоматически при прекращении процесса.

## <a name="hosting-activex-controls-using-atl-axhost"></a>Размещение элементов управления ActiveX, с помощью ATL AXHost

Пример в этом разделе показано, как создать AXHost и как разместить элемент управления ActiveX, с помощью различных функций ATL. Также показано, как для доступа к событиям элемента управления и в качестве приемника (с помощью [IDispEventImpl](../atl/reference/idispeventimpl-class.md)) из элемента управления, который размещается. Этот образец размещает элемент управления Calendar в главном окне или в дочернем окне.

Обратите внимание, что определение `USE_METHOD` символов. Можно изменить значение этого символа, чтобы принимать значения от 1 до 8. Значение символа определяет, как будет создан элемент управления:

- Для значений с четными номерами `USE_METHOD`, вызов для создания узла подклассы окна и преобразует его в узел управления. Для нечетные значения код создает дочернее окно, который выступает в качестве узла.

- Для значений `USE_METHOD` от 1 до 4, доступ к элементу управления и прием событий, выполняются в вызове, также создает узел. Значения в диапазоне от 5 до 8 запроса узла для интерфейсов и подключить приемника.

Ниже приведена сводная информация о вариантах.

|USE_METHOD|Ведущее приложение|Управление доступом и прием|Демонстрируются функции|
|-----------------|----------|--------------------------------------|---------------------------|
|1|Дочернее окно|Один шаг|CreateControlLicEx|
|2|Главное окно|Один шаг|AtlAxCreateControlLicEx|
|3|Дочернее окно|Один шаг|CreateControlEx|
|4|Главное окно|Один шаг|AtlAxCreateControlEx|
|5|Дочернее окно|Несколько шагов|CreateControlLic|
|6|Главное окно|Несколько шагов|AtlAxCreateControlLic|
|7|Дочернее окно|Несколько шагов|CreateControl|
|8|Главное окно|Несколько шагов|AtlAxCreateControl|

[!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]

## <a name="see-also"></a>См. также

[Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)<br/>
[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)<br/>
[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)<br/>
[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[Класс CAxWindow2T](../atl/reference/caxwindow2t-class.md)<br/>
[Интерфейс IAxWinHostWindowLic](../atl/reference/iaxwinhostwindowlic-interface.md)