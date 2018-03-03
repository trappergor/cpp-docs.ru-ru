---
title: "Создание приложения с контейнером активных документов | Документы Microsoft"
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
- active documents [MFC], containers
- containers [MFC], active document
- active document containers [MFC], creating
- MFC COM, active document containment
- applications [MFC], active document container
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 077d15837ed857ac983c3c9f9d4e7853b45aeee5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-active-document-container-application"></a>Создание приложения с контейнером активных документов
Простейшим и наиболее рекомендуемый способ создания приложения с контейнером активных документов является создание приложения MFC EXE контейнера с помощью мастера приложений MFC, а затем измените приложения для поддержки вложения активного документа.  
  
#### <a name="to-create-an-active-document-container-application"></a>Для создания приложения с контейнером активных документов  
  
1.  Из **файл** меню, нажмите кнопку **проекта**из **New** подменю.  
  
2.  В левой области щелкните **Visual C++** тип проекта.  
  
3.  Выберите **приложение MFC** на правой панели.  
  
4.  Назовите проект `MyProj`, нажмите кнопку **ОК**.  
  
5.  Выберите **поддержка составных документов** страницы.  
  
6.  Выберите **контейнера** или **контейнера, Full-server** параметр.  
  
7.  Выберите **контейнер активного документа** флажок.  
  
8.  Нажмите кнопку **Готово**.  
  
9. Когда мастер приложений MFC завершит создание приложения, откройте следующие файлы с помощью обозревателя решений:  
  
    -   MyProjview.cpp  
  
10. В MyProjview.cpp внесите следующие изменения:  
  
    -   В `CMyProjView::OnPreparePrinting`, замените содержимое функции с помощью следующего кода:  
  
         [!code-cpp[NVC_MFCDocView#56](../mfc/codesnippet/cpp/creating-an-active-document-container-application_1.cpp)]  
  
     `OnPreparePrinting`предоставляет поддержку печати. Этот код заменяет `DoPreparePrinting`, который является подготовки печати по умолчанию.  
  
     Вложение активного документа предоставляет Улучшенная схема печати:  
  
    -   Сначала можно вызвать активного документа по его `IPrint` интерфейса и указал сам. Это отличается от предыдущих вложения OLE, в котором были контейнера для отрисовки рисунка содержащегося элемента в принтер `CDC` объекта.  
  
    -   В случае неудачи сообщите содержащегося элемента для печати сам себя через его `IOleCommandTarget` интерфейса  
  
    -   Если это не удается сделайте отрисовку элемента.  
  
     Статические функции-члены `COleDocObjectItem::OnPrint` и `COleDocObjectItem::OnPreparePrinting`, как реализована в предыдущем коде обрабатывать это улучшенная схема для печати.  
  
11. Добавьте любой реализации и построения приложения.  
  
## <a name="see-also"></a>См. также  
 [Вложение активного документа](../mfc/active-document-containment.md)

