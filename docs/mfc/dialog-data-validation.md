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
ms.openlocfilehash: 99540214d1b903c66d350145c08ab657d12ef8f7
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616758"
---
# <a name="dialog-data-validation"></a>Проверка данных диалогового окна

Можно указать проверку в дополнение к обмену данными, вызвав функции DDV, как показано в примере в [диалоговом окне обмена данными в диалоговых окнах](dialog-data-exchange.md). `DDV_MaxChars`Вызов в примере проверяет, что строка, указанная в элементе управления "текстовое поле", не длиннее 20 символов. Функция DDV обычно оповещает пользователя о наличии окна сообщения в случае сбоя проверки и помещает фокус на элемент управления, вызвавший ошибку, чтобы пользователь мог повторно ввести данные. Функция DDV для данного элемента управления должна вызываться сразу после функции DDX для того же элемента управления.

Вы также можете определить собственные пользовательские подпрограммы DDX и DDV. Дополнительные сведения об этом и других аспектах DDX и DDV см. в [техническом заметке MFC 26](tn026-ddx-and-ddv-routines.md).

[Мастер добавления переменной члена](../ide/add-member-variable-wizard.md) будет записывать все вызовы DDX и DDV в карте данных.

## <a name="see-also"></a>См. также раздел

[Обмен данными диалоговых окон и их проверка](dialog-data-exchange-and-validation.md)<br/>
[Работа с диалоговыми окнами в MFC](life-cycle-of-a-dialog-box.md)<br/>
[Обмен данными диалоговых окон](dialog-data-exchange.md)
