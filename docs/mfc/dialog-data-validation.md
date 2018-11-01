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
ms.openlocfilehash: 2283806d3fe7c4ff6bd3abc2ae6a86f5dd176d10
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483359"
---
# <a name="dialog-data-validation"></a>Проверка данных диалогового окна

Можно указать проверки помимо обмена данными путем вызова функции DDV к элементам Управления, как показано в примере в [обмен данными диалоговых окон](../mfc/dialog-data-exchange.md). `DDV_MaxChars` Вызова в примере проверяет, что строка, введенная в элементе управления текстового поля не длиннее 20 символов. Функция DDV обычно предупреждает пользователя в окне сообщения, если проверка завершается неудачно и помещает фокус в элемент управления, вызвавший ошибку, поэтому пользователь может повторно ввести данные. Функция DDV к элементам Управления для заданного элемента управления должен вызываться сразу же после функции DDX для одного элемента управления.

Можно также определить собственные пользовательские процедуры DDX и DDV к элементам Управления. Дополнительные сведения об этом и других аспектов DDX и DDV к элементам Управления, см. в разделе [MFC технические Примечание 26](../mfc/tn026-ddx-and-ddv-routines.md).

[Член мастер добавления переменной-](../ide/add-member-variable-wizard.md) будет записывать все DDX и DDV вызовов в сопоставление данных для вас.

## <a name="see-also"></a>См. также

[Обмен данными диалоговых окон и их проверка](../mfc/dialog-data-exchange-and-validation.md)<br/>
[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Обмен данными диалоговых окон](../mfc/dialog-data-exchange.md)

