---
title: "Создание модальных диалоговых окон | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "диалоговые окна MFC, создание"
  - "диалоговые окна MFC, модальные"
  - "модальные диалоговые окна, создание"
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Создание модальных диалоговых окон
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для создания модального диалогового окна вызовите один из 2 открытых конструкторов, объявленных в [CDialog](../mfc/reference/cdialog-class.md).  Далее, необходимо вызвать функцию\-член [Метод DoModal](../Topic/CDialog::DoModal.md) объекта диалогового окна для отображения диалогового окна и для управления взаимодействие с ним до тех пор, пока пользователь не завершит кнопку " ОК ", чтобы выбрать или отменить.  Этот элемент управления `DoModal`, что делает диалоговое окно режимным.  Для модальных окон `DoModal` загружает ресурс диалогового окна.  
  
## См. также  
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)