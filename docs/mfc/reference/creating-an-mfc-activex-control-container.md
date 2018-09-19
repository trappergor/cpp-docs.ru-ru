---
title: Создание контейнеров элементов управления ActiveX MFC | Документация Майкрософт
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7167f00e3abf74d4638bc79615d68ed81fafabf9
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45535123"
---
# <a name="creating-an-mfc-activex-control-container"></a>Создание контейнеров элементов управления MFC ActiveX
Контейнер элементов управления ActiveX — это родительский программа, которая предоставляет среду для элемента управления ActiveX (ранее OLE) для запуска. Можно создать приложение может содержать элементы управления ActiveX с или без использования MFC, но гораздо проще сделать с помощью MFC.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, которые следуют за ActiveX, см. в разделе [элементы управления ActiveX](../activex-controls.md).  
  
 Создания программы контейнера MFC с помощью [мастер приложений MFC](../../mfc/reference/mfc-application-wizard.md) позволяет получить доступ к множество функциональных возможностей элементов управления ActiveX и автоматизации, которые реализуются классами MFC и ActiveX. Эти функции включают Визуальное редактирование, автоматизацию, создание составных файлов и поддержку для элементов управления. Мастер приложений MFC возможности визуального редактирования, которые будет поддерживать родительская программа включать в себя создание контейнера, мини-сервера, full сервера и программу, которая является и контейнером, так и сервера.  
  
-   **Новое приложение MFC**. Чтобы создать новую программу MFC, включает автоматизацию, Визуальное редактирование, составные файлы или поддержку элементов управления, используйте мастер приложений MFC и выбрать соответствующие варианты автоматизации.  
  
-   **Существующее приложение MFC**. При добавлении вложения элемента управления в существующее приложение MFC, см. в разделе [контейнеры элементов управления: вручную Включение OLE вложении элементов управления](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md).  
  
### <a name="to-create-an-activex-container-for-any-of-the-following-types-of-applications"></a>Чтобы создать контейнер ActiveX для любого из следующих типов приложений  
  
1.  [Контейнеры](../../mfc/containers.md)  
  
2.  [Визуальное редактирование](../../mfc/ole-mfc.md)  
  
3.  [Элементы управления ActiveX в MFC](../../mfc/mfc-activex-controls.md)  
  
## <a name="see-also"></a>См. также  
 [Типы проектов Visual C++](../../ide/visual-cpp-project-types.md)

