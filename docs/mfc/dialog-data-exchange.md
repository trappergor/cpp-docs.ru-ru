---
title: Обмен данными диалоговых окон | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae80d7e74c44367b608329ee86633fef6cb510b6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405727"
---
# <a name="dialog-data-exchange"></a>Обмен данными диалоговых окон

При использовании механизма DDX вы задайте начальные значения диалогового окна переменных-членов объекта, обычно в вашей `OnInitDialog` обработчик или диалоговое окно конструктора. Непосредственно перед отображением диалогового окна, механизм DDX перемещает значения из переменных-членов для элементов управления в диалоговом окне, где они отображаются при самого окна появляется в ответ на `DoModal` или `Create`. Реализация по умолчанию `OnInitDialog` в `CDialog` вызовы `UpdateData` функция-член класса `CWnd` для инициализации элементов управления в диалоговом окне.

Тот же механизм передает значения из элементов управления в переменных-членов при нажатии кнопки "ОК" (или при каждом вызове `UpdateData` функция-член с аргументом **TRUE**). Механизм проверки данных диалогового окна проверяет все элементы данных, для которых указаны правила проверки.

На следующем рисунке показано обмен данными диалоговых окон.

![Обмен данными диалоговых окон поле](../mfc/media/vc379d1.gif "vc379d1") обмен данными диалоговых окон

`UpdateData` работает в обоих направлениях, что определяется **BOOL** ей передан параметр. Для выполнения обмена, `UpdateData` настраивает `CDataExchange` и вызывает класс диалогового окна переопределения `CDialog`в `DoDataExchange` функция-член. `DoDataExchange` принимает аргумент типа `CDataExchange`. `CDataExchange` Передаваемый объект `UpdateData` представляет контекст обмена, определение таких сведений как направление exchange.

Когда вы (или мастера кода) переопределить `DoDataExchange`, укажите вызов одной функции DDX на каждый элемент данных (элемент управления). Каждая функция DDX знает, как для обмена данными в обоих направлениях, исходя из контекста, предоставляемую `CDataExchange` аргумент, передаваемый вашей `DoDataExchange` по `UpdateData`.

MFC предоставляет множество функций DDX для различных видов exchange. В следующем примере показан `DoDataExchange` переопределения, в какие два DDX вызываются функции и одна функция DDV к элементам Управления:

[!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]

`DDX_` И `DDV_` линии — это сопоставление данных. Показано функции DDX и DDV пример — для элемента управления "флажок" и элемент управления поля ввода, соответственно.

Если пользователь отменяет модальное диалоговое окно, `OnCancel` функция-член закрывает диалоговое окно и `DoModal` возвращает значение **IDCANCEL**. В этом случае данные не обмениваются диалоговое окно и объекта диалогового окна.

## <a name="see-also"></a>См. также

[Обмен данными диалоговых окон и их проверка](../mfc/dialog-data-exchange-and-validation.md)<br/>
[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Проверка данных диалогового окна](../mfc/dialog-data-validation.md)

