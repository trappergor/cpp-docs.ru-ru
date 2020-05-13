---
title: Часто задаваемые вопросы о вложении элементов управления ATL
ms.date: 11/04/2016
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
- ATL, hosting ActiveX controls
- ActiveX controls [C++], hosting
- controls [ATL]
ms.assetid: d4bdfbe0-82ca-4f2f-bb95-cb89bdcc9b53
ms.openlocfilehash: 36ff3381447b46b28908522d65be9f34fe23addf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317401"
---
# <a name="atl-control-containment-faq"></a>Часто задаваемые вопросы о вложении элементов управления ATL

## <a name="which-atl-classes-facilitate-activex-control-containment"></a>Какие классы ATL упрощают вложение элементов ActiveX?

Код управления ATL не требует от вас использования каких-либо классов ATL; вы можете просто создать окно **"AtlAxWin80"** и при необходимости использовать API-хостинга управления (для получения дополнительной информации **см.** Тем не менее, следующие классы упрощают использование функций сдерживания.

|Class|Описание|
|-----------|-----------------|
|[CAxWindow](../atl/reference/caxwindow-class.md)|Оберните окно **"AtlAxWin80",** предоставляя методы для создания окна, создания элемента управления и/или крепления элемента управления к окну и извлечения указателей интерфейса на объекте-хоста.|
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|Оберните окно **"AtlAxWinLic80",** предоставляя методы для создания окна, создания элемента управления и/или крепления лицензированного элемента к окну и извлечения указателей интерфейса на объекте-хозяине.|
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|Выступает в качестве базового класса для классов управления ActiveX на основе ресурса диалога. Такие элементы управления могут содержать другие элементы управления ActiveX.|
|[Caxdialogimpl](../atl/reference/caxdialogimpl-class.md)|Действует как базовый класс для классов диалогов на основе ресурса диалога. Такие диалоги могут содержать элементы управления ActiveX.|
|[Cwindow](../atl/reference/cwindow-class.md)|Предоставляет метод, [GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol), который вернет указатель интерфейса на элемент управления, учитывая идентификатор окна его хозяина. Кроме того, обертки Windows `CWindow` API, которые обычно обугчают управление окнами, упрощают управление окнами.|

## <a name="what-is-the-atl-control-hosting-api"></a>Что такое интерфейс API для размещения элементов управления ATL?

API управления ATL — это набор функций, позволяющих любому окну выступать в качестве контейнера управления ActiveX. Эти функции могут быть статически или динамически связаны с проектом, так как они доступны в качестве исходного кода и выставлены ATL90.dll. Функции управления хостингом перечислены в таблице ниже.

|Компонент|Описание|
|--------------|-----------------|
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|Создает объект-хост, соединяет его с поставляемым окном, а затем прикрепляет существующий элемент управления.|
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|Создает объект-хост, подключает его к поставляемому окну, а затем загружает элемент управления.|
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне, подобно [AtlAxCreateControl.](reference/composite-control-global-functions.md#atlaxcreatecontrol)|
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|Создает объект-хост, подключает его к поставляемому окну, затем загружает элемент управления (также позволяет настроить приемники событий).|
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне, подобно [AtlAxCreateControlLic.](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|Создает бесрежимный диалоговый ящик из ресурса диалога и возвращает ручку окна.|
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|Создает модальный диалоговый ящик из ресурса диалогов.|
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|Возвращает **указатель** интерфейса IUnknown элемента управления, размещенного в окне.|
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|Возвращает указатель интерфейса **IUnknown** объекта-хоста, подключенного к окну.|
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|Инициализирует код хостинга управления.|
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|Не инициирует код управления хостингом.|

Параметры `HWND` в первых трех функциях должны быть существующим окном (почти) любого типа. Если вы явно называете любую из этих трех функций (обычно вам не придется), не передавайте ручку окну, которая уже действует в качестве хоста (если вы это сделаете, существующий объект-хоста не будет освобожден).

Первые семь функций называют [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) неявно.

> [!NOTE]
> API, принимающий элемент управления, является основой поддержки ATL для сдерживания управления ActiveX. Тем не менее, как правило, мало нужно называть эти функции непосредственно, если вы воспользоваться или в полной мере использовать atL в обертку классов. Для получения дополнительной информации см., [какие классы ATL облегчают сдерживание управления ActiveX.](which-atl-classes-facilitate-activex-control-containment-q.md)

## <a name="what-is-atlaxwin100"></a>Что такое AtlAxWin100?

`AtlAxWin100`— это название класса окон, которое помогает обеспечить функцию управления atL. При создании экземпляра этого класса процедура окна автоматически использует API-хостинга для создания объекта-хоста, связанного с окном, и загрузки его элементом управления, указанного в качестве названия окна.

## <a name="when-do-i-need-to-call-atlaxwininit"></a>Когда нужно вызывать AtlAxWinInit?

[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) регистрирует класс окон **"AtlAxWin80"** (плюс несколько пользовательских сообщений окон), поэтому эта функция должна быть вызвана, прежде чем пытаться создать окно хоста. Тем не менее, вам не всегда нужно называть эту функцию явно, так как хостинг AIS (и классы, которые их используют) часто называют эту функцию для вас. Нет ничего плохого в том, чтобы звонить по этой функции более одного раза.

## <a name="what-is-a-host-object"></a>Что такое основной объект?

Объект-хоста — объект COM, представляющий контейнер управления ActiveX, поставляемый ATL для определенного окна. Объект-хоста подклассирует окно контейнера так, чтобы он мог отражать сообщения в элемент управления, он обеспечивает необходимые интерфейсы контейнеров, которые будут использоваться элементом управления, и он предоставляет интерфейсы [IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) и [IAxWinAmbientDispatch,](../atl/reference/iaxwinambientdispatch-interface.md) чтобы вы могли настроить среду управления.

Объект-хоста можно использовать для установки свойств окружающей среды контейнера.

## <a name="can-i-host-more-than-one-control-in-a-single-window"></a>Можно ли размещать несколько элементов управления в одном окне?

Невозможно разместить более одного элемента управления в одном окне хоста ATL. Каждое окно хоста предназначено для удержания ровно одного элемента управления за один раз (это позволяет создать простой механизм для обработки отражения сообщений и свойств окружающего элемента). Однако, если пользователю необходимо видеть несколько элементов управления в одном окне, создать несколько окон хоста в качестве детей этого окна.

## <a name="can-i-reuse-a-host-window"></a>Можно ли использовать основное окно повторно?

Не рекомендуется повторно использовать окна хоста. Чтобы обеспечить надежность кода, следует связать срок службы окна хоста со сроком службы одного элемента управления.

## <a name="when-do-i-need-to-call-atlaxwinterm"></a>Когда нужно вызывать AtlAxWinTerm?

[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm) отрегистрирует класс окон **"AtlAxWin80".** Эту функцию следует вызвать (если вам больше не нужно создавать окна хоста) после того, как все существующие окна хоста были уничтожены. Если вы не вызовете эту функцию, класс окон будет автоматически незарегистрирован, когда процесс завершается.

## <a name="hosting-activex-controls-using-atl-axhost"></a>Размещение элементов ActiveX с помощью ATL AXHost

Пример в этом разделе показывает, как создать AXHost и как разместить у себя управление ActiveX с помощью различных функций ATL. Он также показывает, как получить доступ к управлению и раковина событий (с помощью [IDispEventImpl](../atl/reference/idispeventimpl-class.md)) из управления, который размещается. Образец размещает элемент управления календарем в главном окне или в окне ребенка.

Обратите внимание на `USE_METHOD` определение символа. Значение этого символа может варьироваться от 1 до 8. Значение символа определяет способ создания элемента управления:

- Для равномерных значений `USE_METHOD`вызова для создания узла подклассы окна и преобразования его в узла управления. Для значений с нечетным числом код создает окно ребенка, которое действует как униза.

- Для значений `USE_METHOD` от 1 до 4, доступ к управлению и тонущий событий осуществляется в вызов, который также создает хост. Значения от 5 до 8 запроса хоста для интерфейсов и крючок раковины.

Ниже приведена сводная информация о вариантах.

|USE_METHOD|Узел|Управление доступом и погружением событий|Функция продемонстрирована|
|-----------------|----------|--------------------------------------|---------------------------|
|1|Детское окно|Один шаг|СозданиеControlLicEx|
|2|Главное окно|Один шаг|AtlAxCreateControlLicEx|
|3|Детское окно|Один шаг|СозданиеControlEx|
|4|Главное окно|Один шаг|AtlAxCreateControlEx|
|5|Детское окно|Несколько шагов|СоздатьControlLic|
|6|Главное окно|Несколько шагов|AtlAxCreateControlLic|
|7|Детское окно|Несколько шагов|CreateControl|
|8|Главное окно|Несколько шагов|AtlAxCreateControl|

[!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]

## <a name="see-also"></a>См. также раздел

[Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)<br/>
[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)<br/>
[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)<br/>
[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)<br/>
[Класс CAxWindow2T](../atl/reference/caxwindow2t-class.md)<br/>
[Интерфейс IAxWinHostWindowLic](../atl/reference/iaxwinhostwindowlic-interface.md)
