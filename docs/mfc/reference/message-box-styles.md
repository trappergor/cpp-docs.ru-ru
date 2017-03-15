---
title: "Стили окна сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MB_ICONQUESTION"
  - "MB_ICONINFORMATION"
  - "MB_DEFBUTTON2"
  - "MB_YESNO"
  - "MB_OKCANCEL"
  - "MB_TASKMODAL"
  - "MB_ICONEXCLAMATION"
  - "MB_OK"
  - "MB_DEFBUTTON3"
  - "MB_YESNOCANCEL"
  - "MB_APPLMODAL"
  - "MB_RETRYCANCEL"
  - "MB_DEFBUTTON1"
  - "MB_ABORTRETRYIGNORE"
  - "MB_SYSTEMMODAL"
  - "MB_ICONSTOP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MB_ABORTRETRYIGNORE - константа"
  - "MB_APPLMODAL - константа"
  - "MB_DEFBUTTON1 - константа"
  - "MB_DEFBUTTON2 - константа"
  - "MB_DEFBUTTON3 - константа"
  - "MB_ICONEXCLAMATION - константа"
  - "MB_ICONINFORMATION - константа"
  - "MB_ICONQUESTION - константа"
  - "MB_ICONSTOP - константа"
  - "MB_OK - константа"
  - "MB_OKCANCEL - константа"
  - "MB_RETRYCANCEL - константа"
  - "MB_SYSTEMMODAL - константа"
  - "MB_TASKMODAL - константа"
  - "MB_YESNO - константа"
  - "MB_YESNOCANCEL - константа"
  - "стили окна сообщений"
ms.assetid: d87014c5-4ea4-4950-a27e-7bcdda67be7d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Стили окна сообщений
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Следующие стили окна сообщений.  
  
## Типы Message\_Box  
  
-   Окно сообщения содержит **MB\_ABORTRETRYIGNORE** 3 кнопки. Прервите, итерации и ignore.  
  
-   Окно сообщения **MB\_OK** содержит одну кнопку: ОК.  
  
-   Окно сообщения содержит **MB\_OKCANCEL** 2 кнопки. " ОК " и " Отмена ".  
  
-   Окно сообщения содержит **MB\_RETRYCANCEL** 2 кнопки. Отмены и повтора.  
  
-   Окно сообщения содержит **MB\_YESNO** 2 кнопки. Да и нет.  
  
-   Окно сообщения содержит **MB\_YESNOCANCEL** 3 кнопки. Да, нет и Отмена.  
  
## Модальность окна сообщения  
  
-   **MB\_APPLMODAL** пользователь должен реагировать на окно сообщения для продолжения работы в текущем окне.  Однако пользователь может перемещать окна других приложений и работать в этих окнах.  Значение по умолчанию **MB\_APPLMODALMB\_SYSTEMMODAL** и **MB\_TASKMODAL**, если не определены.  
  
-   **MB\_SYSTEMMODAL** все приложения приостановлено до тех пор, пока пользователь не будет реагировать на окно сообщения.  Системой тогда окна сообщения используются, чтобы уведомить пользователя, что дискредитирующих серьезных ошибок, требующие немедленного внимания и следует использовать осторожно.  
  
-   **MB\_TASKMODAL** аналогична **MB\_APPLMODAL**, но не является удобным в приложении класса Microsoft Foundation.  Этот флажок зарезервировано для вызывающего приложения или библиотеки, которая не имеет дескриптор окна.  
  
## Значки окна сообщения  
  
-   Значок **MB\_ICONEXCLAMATION** восклицательного знака отображается в окне сообщения.  
  
-   **MB\_ICONINFORMATION** состоять из Значка «i» в круге появляюсь в окне сообщения.  
  
-   Значок **MB\_ICONQUESTION** a вопрос\- метки отображается в окне сообщения.  
  
-   Значок остановка\- подписи **MB\_ICONSTOP** a отображается в окне сообщения.  
  
## Кнопка по умолчанию окна сообщения  
  
-   Первая кнопка **MB\_DEFBUTTON1** по умолчанию.  Обратите внимание, что первая кнопка всегда по умолчанию, если **MB\_DEFBUTTON2** или **MB\_DEFBUTTON3** не определены.  
  
-   Вторая кнопка **MB\_DEFBUTTON2** по умолчанию.  
  
-   Третья кнопка **MB\_DEFBUTTON3** по умолчанию.  
  
## См. также  
 [Стили, используемые MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [AfxMessageBox](../Topic/AfxMessageBox.md)