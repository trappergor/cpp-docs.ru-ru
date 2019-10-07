---
title: Проверка данных диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
ms.openlocfilehash: c89ed82b148062ddb64fa85eaabda12f44e59895
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685771"
---
# <a name="dialog-data-validation"></a>Проверка данных диалогового окна

Можно указать проверку в дополнение к обмену данными, вызвав функции DDV, как показано в примере в [диалоговом окне обмена данными в диалоговых окнах](../mfc/dialog-data-exchange.md). Вызов `DDV_MaxChars` в примере проверяет, что строка, указанная в элементе управления "текстовое поле", не длиннее 20 символов. Функция DDV обычно оповещает пользователя о наличии окна сообщения в случае сбоя проверки и помещает фокус на элемент управления, вызвавший ошибку, чтобы пользователь мог повторно ввести данные. Функция DDV для данного элемента управления должна вызываться сразу после функции DDX для того же элемента управления.

Вы также можете определить собственные пользовательские подпрограммы DDX и DDV. Дополнительные сведения об этом и других аспектах DDX и DDV см. в [техническом заметке MFC 26](../mfc/tn026-ddx-and-ddv-routines.md).

[Мастер добавления переменной члена](../ide/add-member-variable-wizard.md) будет записывать все вызовы DDX и DDV в карте данных.

## <a name="see-also"></a>См. также

[Обмен данными диалоговых окон и их проверка](../mfc/dialog-data-exchange-and-validation.md)<br/>
[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Обмен данными диалоговых окон](../mfc/dialog-data-exchange.md)
