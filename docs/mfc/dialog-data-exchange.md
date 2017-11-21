---
title: "Обмен данными диалоговых окон | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e6da394a91eab08f0c79b3edb33132e3c85401af
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="dialog-data-exchange"></a>Обмен данными диалоговых окон
При использовании механизма DDX можно задать начальные значения диалогового окна переменных-членов объекта, обычно в вашей `OnInitDialog` обработчик или диалогового окна конструктора. Непосредственно перед отображением диалогового окна механизм DDX перемещает значения переменных-членов для элементов управления в диалоговом окне, где они отображаются при самого окна появляется в ответ на `DoModal` или **создать** . Реализация по умолчанию `OnInitDialog` в `CDialog` вызовы `UpdateData` функции-члена класса `CWnd` для инициализации элементов управления в диалоговом окне.  
  
 Тот же механизм передает значения из элементов управления для переменных-членов при нажатии кнопки «ОК» (или при каждом вызове `UpdateData` функция-член с аргументом **TRUE**). Механизм проверки данных диалогового окна проверяет все элементы данных, для которых задан правила проверки.  
  
 На следующем рисунке показана обмен данными диалоговых окон.  
  
 ![Обмен данными](../mfc/media/vc379d1.gif "vc379d1")  
Обмен данными диалоговых окон  
  
 `UpdateData`работает в обоих направлениях, определяемое параметром **BOOL** ей передан параметр. Для выполнения обмена, `UpdateData` настраивает `CDataExchange` и вызывает переопределение класса диалогового окна `CDialog` `DoDataExchange` функции-члена. `DoDataExchange`принимает аргумент типа `CDataExchange`. `CDataExchange` Передаваемый объект `UpdateData` представляет контекст exchange, определение такие сведения как направление exchange.  
  
 Когда вы (или мастера создания кода) переопределить `DoDataExchange`, укажите вызова одной функции DDX на каждый элемент данных (элемент управления). Каждая функция DDX знает, как обмен данными в обоих направлениях, в зависимости от контекста, предоставляемые `CDataExchange` аргумент, передаваемый вашей `DoDataExchange` по `UpdateData`.  
  
 MFC предоставляет множество функций DDX для различных видов exchange. В следующем примере показан `DoDataExchange` переопределения, в которой два DDX называются одна функция DDV и функции:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#49](../mfc/codesnippet/cpp/dialog-data-exchange_1.cpp)]  
  
 `DDX_` И `DDV_` строки представляют собой сопоставления данных. Показано функции DDX и DDV образец: для элемента управления флажок и элемент управления поля ввода.  
  
 Если пользователь отменяет модальным диалоговым окном, `OnCancel` закрывает диалоговое окно функции-члена и `DoModal` возвращает значение **IDCANCEL**. В этом случае данные не обмениваются диалогового окна и объекта диалогового окна.  
  
## <a name="see-also"></a>См. также  
 [Диалоговое окно данных Exchange и проверки](../mfc/dialog-data-exchange-and-validation.md)   
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)   
 [Проверка данных диалогового окна](../mfc/dialog-data-validation.md)

