---
title: "Проверка данных диалогового окна | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- validating data [MFC], message boxes
- data validation [MFC], dialog boxes
- dialog boxes [MFC], validating data
- validating data [MFC], dialog box data entry
- DDV (dialog data validation) [MFC]
- data validation [MFC], message boxes
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 01766dd741ed87d9ac11b8858221a1bd09b0cf31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dialog-data-validation"></a>Проверка данных диалогового окна
Можно указать проверки помимо обмена данными путем вызова функции DDV, как показано в примере в [обмен данными диалоговых окон](../mfc/dialog-data-exchange.md). `DDV_MaxChars` Вызов в примере проверяет, что строка, введенная в текстовое поле элемента управления не больше 20 символов. Обычно функция DDV предупреждает пользователя в окне сообщения, если проверка завершается ошибкой и помещает фокус на элемент управления, вызвавший ошибку, пользователь может вводить данные. Функция DDV определенного элемента управления должен вызываться сразу после функции DDX для одного элемента управления.  
  
 Можно также определить собственные пользовательские процедуры DDX и DDV. Дополнительные сведения об этом и других аспектов DDX и DDV см. в разделе [MFC Технические заметки 26](../mfc/tn026-ddx-and-ddv-routines.md).  
  
 [Член мастер добавления переменной-](../ide/add-member-variable-wizard.md) напишете весь DDX и DDV вызовов в сопоставление данных для вас.  
  
## <a name="see-also"></a>См. также  
 [Диалоговое окно данных Exchange и проверки](../mfc/dialog-data-exchange-and-validation.md)   
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)   
 [Обмен данными диалоговых окон](../mfc/dialog-data-exchange.md)

