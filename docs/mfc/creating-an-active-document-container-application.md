---
title: Создание приложения с контейнером активных документов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- active document containers [MFC], creating
- MFC COM, active document containment
- applications [MFC], active document container
ms.assetid: 14e2d022-a6c5-4249-8712-706b0f4433f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1b20dd592e180122e119b08ab59babfdaae8d54
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052818"
---
# <a name="creating-an-active-document-container-application"></a>Создание приложения с контейнером активных документов

Простейший и наиболее рекомендуемый способ создания приложения с контейнером активных документов является создание приложения-контейнера MFC EXE-файла с помощью мастера приложений MFC, а затем измените приложение для поддержки вложения активного документа.

#### <a name="to-create-an-active-document-container-application"></a>Для создания приложения с контейнером активных документов

1. Из **файл** меню, щелкните **проекта**из **New** подменю.

1. В левой области щелкните **Visual C++** тип проекта.

1. Выберите **приложения MFC** на правой панели.

1. Назовите проект *MyProj*, нажмите кнопку **ОК**.

1. Выберите **поддержка составных документов** страницы.

1. Выберите **контейнера** или **контейнера/полносерверные** параметр.

1. Выберите **контейнер активного документа** "флажок".

1. Нажмите кнопку **Готово**.

9. Когда мастер приложений MFC завершит создание приложения, откройте следующие файлы в обозревателе решений:

   - *MyProjview.cpp*

10. В *MyProjview.cpp*, внесите следующие изменения:

   - В `CMyProjView::OnPreparePrinting`, замените содержимое функции следующим кодом:

         [!code-cpp[NVC_MFCDocView#56](../mfc/codesnippet/cpp/creating-an-active-document-container-application_1.cpp)]

   `OnPreparePrinting` предоставляет поддержку печати. Этот код заменяет `DoPreparePrinting`, который является подготовка печати по умолчанию.

   Вложение активного документа предоставляет Улучшенная схема печати:

   - Сначала можно вызвать активного документа по его `IPrint` интерфейс и указал сам. Это отличается от предыдущих вложения OLE, в котором было контейнера для отрисовки рисунка содержащегося элемента в принтер `CDC` объекта.

   - В случае неудачи сообщить содержащегося элемента для печати сам себя через его `IOleCommandTarget` интерфейса

   - В случае неудачи убедитесь в собственной отрисовки элемента.

   Статические функции-члены `COleDocObjectItem::OnPrint` и `COleDocObjectItem::OnPreparePrinting`, реализованный в предыдущем коде обработки Эта улучшенная схема печати.

11. Добавление собственной реализацией и выполните сборку приложения.

## <a name="see-also"></a>См. также

[Вложение активного документа](../mfc/active-document-containment.md)

