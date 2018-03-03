---
title: "Создание окон фрейма документа | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], creating
- document templates [MFC], and document frame windows
- windows [MFC], creating
- runtime, class information
- run-time class [MFC], and document frame window creation
- document frame windows [MFC], creating
- MFC, frame windows
ms.assetid: 8671e239-b76f-4dea-afa8-7024e6e58ff5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9098026c1a38f8e60093415ba1c5a2b3678b64d5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-document-frame-windows"></a>Создание окон фрейма документа
[Создание документов и представлений](../mfc/document-view-creation.md) показано, как [CDocTemplate](../mfc/reference/cdoctemplate-class.md) объекта организует Создание фрейм окна, документ и представление, а затем подключить их все вместе. Три [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) аргументы `CDocTemplate` конструктор укажите фрейм окна, документ и представление классов, шаблона документа создается динамически в ответ на пользователя команд, например команды Создать в файле меню или команду создания окна в меню MDI-окна. Шаблон документа, которые хранятся для последующего использования при создании окно фрейма для представления и документа.  
  
 Для [RUNTIME_CLASS](../mfc/reference/run-time-object-model-services.md#runtime_class) механизм для правильной работы производного фреймового окна классов должны быть объявлены с [DECLARE_DYNCREATE](../mfc/reference/run-time-object-model-services.md#declare_dyncreate) макрос. Это так, как платформа должен создать с помощью механизма динамического создания класса окна фрейма документа `CObject`.  
  
 Когда пользователь выбирает команду, которая создается документ, платформа вызывает шаблон документа, чтобы создать объект документа, представления и окна фрейма, который будет отображать представление. При создании окна фрейма документа, шаблон документа создает объект соответствующего класса — класс, производный от [CFrameWnd](../mfc/reference/cframewnd-class.md) для приложения SDI или из [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) для MDI приложение. Затем вызывается метод объекта окна фрейма [LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) функции-члена для получения сведений по созданию из ресурсов и создания окна Windows. Платформа прикрепляет дескриптор окна фрейма окна объекта. Затем он создает представление как дочернего окна в окне фрейма документа.  
  
 Соблюдайте осторожность при выборе [время инициализации](../mfc/when-to-initialize-cwnd-objects.md) вашей `CWnd`-производного объекта.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Наследование класса от CObject (динамическое создание механизма)](../mfc/deriving-a-class-from-cobject.md)  
  
-   [Создание документов и представлений (шаблоны и Создание окон фрейма)](../mfc/document-view-creation.md)  
  
-   [Уничтожение окон фрейма](../mfc/destroying-frame-windows.md)  
  
## <a name="see-also"></a>См. также  
 [Использование окон фрейма](../mfc/using-frame-windows.md)

