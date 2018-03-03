---
title: "Создание контейнеров элементов управления ActiveX MFC | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.activex.container
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], containers
- ActiveX control containers [MFC], creating
- containers [MFC], creating
- OLE controls [MFC], containers
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2054a11365cc6f9db7a5608f0b056d0d85ff117d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-mfc-activex-control-container"></a>Создание контейнеров элементов управления MFC ActiveX
Контейнер элементов управления ActiveX является родительской программой, которая предоставляет среду для элемента управления ActiveX (ранее OLE) для запуска. Можно создать приложение может содержать элементы управления ActiveX с или без MFC, но гораздо проще сделать с помощью MFC.  
  
 Создание программы контейнера MFC с помощью [мастер приложений MFC](../../mfc/reference/mfc-application-wizard.md) позволяет получить доступ к функциям много элементов управления ActiveX и автоматизацию, реализованную классами MFC и ActiveX. Эти функции включают Визуальное редактирование, автоматизацию, создание составных файлов и поддержку элементов управления. Мастер приложений MFC визуального редактирования поддерживающие родительская программа варианты Создание контейнера, мини-сервера, full сервера и программы, контейнер и сервер.  
  
-   **Новое приложение MFC**. Чтобы создать новую программу MFC, включает автоматизацию, Визуальное редактирование, составные файлы или поддержку элементов управления, использовать мастера приложений MFC и выберите соответствующие параметры автоматизации.  
  
-   **Существующее приложение MFC**. Если добавляются в существующее приложение MFC, см. раздел [контейнеры элементов управления: вручную Включение OLE вложения элемента управления](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md).  
  
### <a name="to-create-an-activex-container-for-any-of-the-following-types-of-applications"></a>Создание контейнера ActiveX для любого из следующих типов приложений  
  
1.  [Контейнеры](../../mfc/containers.md)  
  
2.  [Визуальное редактирование](../../mfc/ole-mfc.md)  
  
3.  [Элементы управления MFC ActiveX](../../mfc/mfc-activex-controls.md)  
  
## <a name="see-also"></a>См. также  
 [Типы проектов Visual C++](../../ide/visual-cpp-project-types.md)

