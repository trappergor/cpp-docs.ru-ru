---
title: Обмен данными диалоговых окон
ms.date: 11/19/2018
helpviewer_keywords:
- initializing dialog boxes
- canceling data exchange
- dialog box data, retrieving
- DDX (dialog data exchange), data exchange mechanism
- dialog boxes [MFC], initializing
- dialog boxes [MFC], retrieving user input using DDX
- dialog box data
- dialog boxes [MFC], data exchange
- CDataExchange class [MFC], using DDX
- DoDataExchange method [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- transferring dialog box data
- DDX (dialog data exchange), canceling
- UpdateData method [MFC]
- retrieving dialog box data [MFC]
ms.assetid: 4675f63b-41d2-45ed-b6c3-235ad8ab924b
ms.openlocfilehash: 9a0199577ea46520c2eadc308812de8a1ce4b514
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685812"
---
# <a name="dialog-data-exchange"></a>Обмен данными диалоговых окон

Если используется механизм DDX, то начальные значения переменных-членов объекта диалогового окна обычно задаются в обработчике `OnInitDialog` или конструкторе диалогового окна. Непосредственно перед отображением диалогового окна механизм DDX платформы передает значения переменных-членов в элементы управления в диалоговом окне, где они появляются, когда диалоговое окно отображается в ответ на `DoModal` или `Create`. Реализация по умолчанию `OnInitDialog` в `CDialog` @no__t вызывает функцию-член класса `CWnd`, чтобы инициализировать элементы управления в диалоговом окне.

Тот же механизм передает значения из элементов управления в переменные-члены, когда пользователь нажимает кнопку ОК (или при каждом вызове функции-члена @no__t – 0 с аргументом **true**). Механизм проверки данных диалогового окна проверяет все элементы данных, для которых были указаны правила проверки.

На следующем рисунке показан обмен данными в диалоговом окне.

Диалоговое окно ![обмена данными](../mfc/media/vc379d1.gif "диалоговое окно обмен данными") <br/>
Обмен данными диалоговых окон

`UpdateData` работает в обоих направлениях, как указано в переданном параметре **bool** . Чтобы выполнить сервер Exchange, `UpdateData` настраивает объект `CDataExchange` и вызывает переопределение класса диалогового окна функции-члена `CDialog` @no__t 3. `DoDataExchange` принимает аргумент типа `CDataExchange`. Объект `CDataExchange`, передаваемый в `UpdateData`, представляет контекст обмена, определяя такие сведения в качестве направления обмена.

Когда вы (или мастер кода) переопределяете `DoDataExchange`, вы указываете вызов одной функции DDX на каждый элемент данных (Control). Каждая функция DDX знает, как обмениваться данными в обоих направлениях на основе контекста, предоставленного аргументом `CDataExchange`, передаваемым в `DoDataExchange` с помощью `UpdateData`.

MFC предоставляет множество функций DDX для различных видов обмена. В следующем примере показано переопределение `DoDataExchange`, в котором вызываются две функции DDX и одна функция DDV:

[!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]

Строки `DDX_` и `DDV_` представляют собой карту данных. Приведенные ниже примеры функций DDX и DDV предназначены для элемента управления "флажок" и элемента управления "поле ввода" соответственно.

Если пользователь отменяет модальное диалоговое окно, функция-член @no__t – 0 завершает диалоговое окно, а `DoModal` возвращает значение **идканцел**. В этом случае обмен данными между диалоговым окном и объектом диалогового окна не происходит.

## <a name="see-also"></a>См. также

[Обмен данными диалоговых окон и их проверка](../mfc/dialog-data-exchange-and-validation.md)<br/>
[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Проверка данных диалогового окна](../mfc/dialog-data-validation.md)
