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
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "71685812"
---
# <a name="dialog-data-exchange"></a>Обмен данными диалоговых окон

При использовании механизма DDX задаются начальные значения переменных члена объекта диалогового окна, обычно в обработчике `OnInitDialog` или конструкторе диалогового окна. Непосредственно перед отображением диалогового окна механизм DDX платформы передает значения переменных-членов в элементы управления в диалоговом окне, где они появляются, когда диалоговое окно отображается в ответ на `DoModal` или `Create`. Реализация `OnInitDialog` по умолчанию в `CDialog` вызывает функцию `UpdateData` члена класса `CWnd` для инициализации элементов управления в диалоговом окне.

Тот же механизм передает значения из элементов управления в переменные-члены, когда пользователь нажимает кнопку ОК (или при каждом вызове функции члена `UpdateData` с аргументом **true**). Механизм проверки данных диалогового окна проверяет все элементы данных, для которых были указаны правила проверки.

На следующем рисунке показан обмен данными в диалоговом окне.

![Обмен данными в диалоговом окне](../mfc/media/vc379d1.gif "Обмен данными диалоговых окон") <br/>
Обмен данными диалоговых окон

`UpdateData` работает в обоих направлениях, как указано параметром **bool** , передаваемым ему. Для выполнения Exchange `UpdateData` настраивает `CDataExchange` объект и вызывает переопределение класса диалогового окна `CDialog` функции-члена `DoDataExchange`. `DoDataExchange` принимает аргумент типа `CDataExchange`. Объект `CDataExchange`, передаваемый в `UpdateData`, представляет контекст обмена, определяющий такие сведения, как направление обмена.

Когда вы (или мастер кода) переопределяете `DoDataExchange`, вы указываете вызов одной функции DDX на каждый элемент данных (Control). Каждая функция DDX знает, как обмениваться данными в обоих направлениях на основе контекста, предоставленного аргументом `CDataExchange`, передаваемым в `DoDataExchange` `UpdateData`.

MFC предоставляет множество функций DDX для различных видов обмена. В следующем примере показано переопределение `DoDataExchange`, в котором вызываются две функции DDX и одна функция DDV:

[!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]

Строки `DDX_` и `DDV_` являются картой данных. Приведенные ниже примеры функций DDX и DDV предназначены для элемента управления "флажок" и элемента управления "поле ввода" соответственно.

Если пользователь отменяет модальное диалоговое окно, функция-член `OnCancel` завершает диалоговое окно, а `DoModal` возвращает значение **идканцел**. В этом случае обмен данными между диалоговым окном и объектом диалогового окна не происходит.

## <a name="see-also"></a>См. также

[Обмен данными диалоговых окон и их проверка](../mfc/dialog-data-exchange-and-validation.md)<br/>
[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Проверка данных диалогового окна](../mfc/dialog-data-validation.md)
