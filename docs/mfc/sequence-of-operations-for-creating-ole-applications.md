---
title: "Последовательность операций для создания приложений OLE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE applications [MFC], creating
- OLE applications [MFC]
- applications [OLE], creating
- applications [OLE]
ms.assetid: 84b0f606-36c1-4253-9cea-44427f0074b9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db3b5b9a5f4f62fa71cffa37b30a89aee41fe56f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="sequence-of-operations-for-creating-ole-applications"></a>Последовательность операций для создания приложений OLE
Следующая таблица показывает роль и роль платформы при создании OLE связь и внедрение приложения. Они представляют варианты вместо последовательность действий для выполнения.  
  
### <a name="creating-ole-applications"></a>Создание приложения OLE  
  
|Задача|Вы|Платформа делает|  
|----------|------------|------------------------|  
|Создание COM-компонента.|Запустите мастер приложений MFC. Выберите **полный сервер** или **минисерверные** в **поддержка составных документов** вкладки.|Платформа создает схему приложения с включенной возможностью компонент COM. Все возможности модели COM могут передаваться в существующее приложение только незначительные изменения.|  
|Создание приложения-контейнера с нуля.|Запустите мастер приложений MFC. Выберите **контейнера** в **поддержка составных документов** вкладки. С помощью представления классов, перейдите к области редактора исходного кода. Введите код для функций COM обработчика.|Создается общая схема приложения, может вставлять объекты COM, созданные в COM-компонент (сервера) приложения.|  
|Создайте приложение, поддерживающее автоматизации с нуля.|Запустите мастер приложений MFC. Выберите **автоматизации** из **дополнительные функции** вкладки. Представление классов можно используйте для предоставляют методы и свойства приложения для автоматизации.|Платформа создает каркас приложение, которое можно активировать и автоматизировать за счет других приложений.|  
  
## <a name="see-also"></a>См. также  
 [Сборка в платформе](../mfc/building-on-the-framework.md)   
 [Последовательность операций для сборки приложений MFC](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [Последовательность операций для создания элементов управления ActiveX](../mfc/sequence-of-operations-for-creating-activex-controls.md)   
 [Последовательность операций для создания приложений баз данных](../mfc/sequence-of-operations-for-creating-database-applications.md)

