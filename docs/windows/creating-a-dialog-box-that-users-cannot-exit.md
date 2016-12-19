---
title: "Creating a Dialog Box That Users Cannot Exit | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "dialog boxes, creating"
  - "modal dialog boxes, logon screens"
  - "logon screens"
ms.assetid: 54823c27-1658-4388-bd12-0a1ce8f3899e
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Dialog Box That Users Cannot Exit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вы можете создать диалоговое окно времени выполнения, которое не может быть закрыто пользователем. Такой тип диалогового окна используется для входа в систему, блокирования приложений или документов.  
  
### Создание диалогового окна, которое не может быть закрыто пользователем  
  
1.  В области **Свойства** диалогового окна задайте для свойства **Системное меню** значение **false**.  
  
     Это приведет к отключению системного меню диалогового окна и кнопки **Закрыть**.  
  
2.  В форме диалогового окна удалите кнопки **Отмена** и **ОК**.  
  
     Во время выполнения пользователь не может закрыть модальное диалоговое окно с такими характеристиками.  
  
 Чтобы обеспечить возможность тестирования этого вида диалоговых окон, функция тестирования диалогового окна распознает нажатие клавиши ESC. \(Клавиша ESC также известна как виртуальная клавиша VK\_ESCAPE.\) Вне зависимости от того, какое поведение будет у диалогового окна во время выполнения, вы сможете закрыть его в тестовом режиме нажатием клавиши ESC.  
  
> [!NOTE]
>  Для создания диалогового окна, которое не может быть закрыто пользователем, в приложении MFC необходимо переопределить поведение `OnOK`и `OnCancel` по умолчанию, так как даже если удалить соответствующие кнопки, диалоговое окно все равно можно закрыть нажатием клавиши ВВОД или ESC.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [Ресурсы в приложениях для настольных систем](../Topic/Resources%20in%20Desktop%20Apps.md).  
  
## Требования  
 Win32  
  
## См. также  
 [How to: Create a Resource](../windows/how-to-create-a-resource.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Dialog Editor](../mfc/dialog-editor.md)