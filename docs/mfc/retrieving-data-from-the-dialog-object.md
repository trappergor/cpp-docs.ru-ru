---
title: Извлечение данных из объекта диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], retrieving user data
- dialog box data [MFC]
- data [MFC], retrieving
- GetDlgItemText method [MFC]
- SetDlgItemText method [MFC]
- SetWindowText method [MFC]
- dialog box data [MFC], retrieving
- retrieving data [MFC]
- user input [MFC], retrieving from MFC dialog boxes
- capturing user input [MFC]
- dialog box controls [MFC], initializing values
- DDX (dialog data exchange) [MFC]
- MFC dialog boxes [MFC], retrieving user input
- data retrieval [MFC], dialog boxes
- data [MFC], dialog boxes
- DDX (dialog data exchange) [MFC], about DDX
- DDX (dialog data exchange) [MFC], retrieving data from Dialog object
- GetWindowText method [MFC]
ms.assetid: bdca2b61-6b53-4c2e-b426-8712c7a38ec0
ms.openlocfilehash: 345a2894693eace5aa464ca3940c785b2da08784
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615137"
---
# <a name="retrieving-data-from-the-dialog-object"></a>Извлечение данных из объекта диалогового окна

Платформа предоставляет простой способ для инициализации значений элементов управления в диалоговом окне и для извлечения значений из элементов управления. Более трудный вручную подход заключается в вызове функции, например `SetDlgItemText` и `GetDlgItemText` функции-члены класса `CWnd`, которые действуют для элемента управления windows. С этими функциями, вы каждый управление доступом по отдельности, чтобы задать или получить свое значение, вызов функций, таких как `SetWindowText` и `GetWindowText`. Платформы подхода автоматизирует инициализации и извлечения.

Обмен данными диалоговых окон (DDX) позволяет упростить обмен данными между элементы управления в диалоговое окно переменные поле и член в объекте диалогового окна. Такой обмен работает в обоих направлениях. Для инициализации элементов управления в диалоговом окне, можно задать значения членов данных в объекте диалогового окна, а платформа будет передавать значения к элементам управления, прежде чем откроется диалоговое окно. Вы можете в любое время обновить элементы данных диалоговое окно с данными, введенный пользователем. В таком случае можно использовать данные, ссылаясь на переменных-членов данных.

Можно также расположить для значений элементов управления диалоговых окон, проверенных автоматически с помощью проверка данных диалогового окна (DDV).

DDX и DDV к элементам Управления описаны более подробно в [обмен данными диалоговых окон и проверка](../mfc/dialog-data-exchange-and-validation.md).

Для модального диалогового окна, можно получить все данные, введенные пользователем, когда `DoModal` возвращает IDOK, но объект уничтожается перед диалогового окна. Для немодального диалогового окна, можно получить данные из объекта диалогового окна в любое время, вызвав `UpdateData` с аргументом **TRUE** и доступа к переменным-членам класса диалогового окна. Этой теме рассматривается более подробно в [обмен данными диалоговых окон и проверка](../mfc/dialog-data-exchange-and-validation.md).

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

