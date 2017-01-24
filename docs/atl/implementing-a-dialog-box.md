---
title: "Implementing a Dialog Box | Microsoft Docs"
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
  - "ATL - библиотека, диалоговые окна"
  - "CAxDialogImpl class, implementing dialog boxes in ATL"
  - "CSimpleDialog class, implementing dialog boxes in ATL"
  - "диалоговые окна, ATL - библиотека"
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 Способа диалоговое окно добавление в проект библиотеки ATL: используйте мастер диалогового окна библиотеки ATL или добавить его вручную.  
  
## Диалоговое окно добавить с помощью мастера диалогового окна библиотеки ATL  
 В [Диалоговое окно " добавление класса](../ide/add-class-dialog-box.md) выберите объект диалогового окна библиотеку ATL для диалоговое окно добавление в проект библиотеки ATL.  Заполните мастер диалогового окна библиотеки ATL, как соответствующее и нажмите кнопку **Готово**.  Мастер добавит класс, производный от [CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md) в проект.  Откройте представление ресурсов из меню **Вид** найдите диалоговое окно, и дважды щелкните его, чтобы открыть его в редакторе ресурсов.  
  
> [!NOTE]
>  Если диалоговое окно выводится из `CAxDialogImpl`, то оно может размещения и управления ActiveX и Windows.  Если вы не хотите издержки поддержки элементов управления ActiveX в классе диалогового окна, используйте [CSimpleDialog](../atl/reference/csimpledialog-class.md) или [CDialogImpl](../Topic/CDialogImpl%20Class.md).  
  
 Сообщение и обработчики событий можно добавлять к классу диалогового окна из представления класса.  Дополнительные сведения см. в разделе [Добавление обработчика сообщений ATL](../atl/adding-an-atl-message-handler.md).  
  
## Добавление диалоговое окно вручную  
 Реализация диалоговое окно аналогично реализация окно.  Необходимо создать производный класс от или [CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md), [CDialogImpl](../Topic/CDialogImpl%20Class.md) или [CSimpleDialog](../atl/reference/csimpledialog-class.md) и объявить [сопоставление сообщений](../atl/message-maps-atl.md) для обработки сообщения.  Однако необходимо также указать идентификатор ресурса шаблона диалоговых окон в производном классе.  Пользовательский класс должен иметь элемент данных с именем `IDD`, чтобы оставить это значение.  
  
> [!NOTE]
>  При создании диалоговое окно с помощью мастера диалогового окна библиотеки ATL мастер автоматически добавляет элемент `IDD` как тип `enum`.  
  
 `CDialogImpl` позволяет реализовать диалоговое окно режимного или немодального то управления Windows узлов.  `CAxDialogImpl` позволяет реализовать диалоговое окно режимного или немодального, размещение и управления ActiveX и Windows.  
  
 Для создания модального диалогового окна, создайте экземпляр производного `CDialogImpl`\(или производный класс `CAxDialogImpl`\-\) и затем вызывает метод [DoModal](../Topic/CDialogImpl::DoModal.md).  Чтобы закрыть модального диалогового окна, вызовите метод [EndDialog](../Topic/CDialogImpl::EndDialog.md) из обработчика сообщений.  Для создания безрежимного диалогового окна, вызовите метод [Создание](../Topic/CDialogImpl::Create.md) вместо `DoModal`.  Уничтожить безрежимное диалоговое окно, вызов [DestroyWindow](../Topic/CDialogImpl::DestroyWindow.md).  
  
 Тонуть события автоматически выполняется в [CAxDialogImpl](../Topic/CAxDialogImpl%20Class.md).  Реализуйте обработчики сообщений диалогового окна, как обработчики в `CWindowImpl`\- производный класс.  Если возвращаемое значение сообщение\- определенной, верните ее в качестве `LRESULT`.  Возвращаемые значения `LRESULT` сопоставлены библиотеки ATL для правильной обработки диспетчером диалогового окна Windows.  Дополнительные сведения см. в разделе исходный код для [CDialogImplBaseT::DialogProc](../Topic/CDialogImpl::DialogProc.md) в atlwin.h.  
  
## Пример  
 Следующий класс реализует диалоговое окно:  
  
 [!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/CPP/implementing-a-dialog-box_1.h)]  
  
## См. также  
 [Классы окон](../Topic/ATL%20Window%20Classes.md)