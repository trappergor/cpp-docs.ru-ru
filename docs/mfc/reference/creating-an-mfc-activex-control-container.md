---
title: Создание контейнеров элементов управления MFC ActiveX
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.activex.container
helpviewer_keywords:
- MFC ActiveX controls [MFC], containers
- ActiveX control containers [MFC], creating
- containers [MFC], creating
- OLE controls [MFC], containers
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
ms.openlocfilehash: f0d5fe419375535ab8c52378b9005df88634e99a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57275900"
---
# <a name="creating-an-mfc-activex-control-container"></a>Создание контейнеров элементов управления MFC ActiveX

Контейнер элементов управления ActiveX — это родительский программа, которая предоставляет среду для элемента управления ActiveX (ранее OLE) для запуска. Можно создать приложение может содержать элементы управления ActiveX с или без использования MFC, но гораздо проще сделать с помощью MFC.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, заменяющие ActiveX, см. в разделе [элементы управления ActiveX](../activex-controls.md).

Создания программы контейнера MFC с помощью [мастер приложений MFC](../../mfc/reference/mfc-application-wizard.md) позволяет получить доступ к множество функциональных возможностей элементов управления ActiveX и автоматизации, которые реализуются классами MFC и ActiveX. Эти функции включают Визуальное редактирование, автоматизацию, создание составных файлов и поддержку для элементов управления. Мастер приложений MFC возможности визуального редактирования, которые будет поддерживать родительская программа включать в себя создание контейнера, мини-сервера, full сервера и программу, которая является и контейнером, так и сервера.

- **Новое приложение MFC**. Чтобы создать новую программу MFC, включает автоматизацию, Визуальное редактирование, составные файлы или поддержку элементов управления, используйте мастер приложений MFC и выбрать соответствующие варианты автоматизации.

- **Существующее приложение MFC**. При добавлении вложения элемента управления в существующее приложение MFC, см. в разделе [контейнеры элементов управления: Включение вложения элемента управления OLE вручную](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md).

### <a name="to-create-an-activex-container-for-any-of-the-following-types-of-applications"></a>Чтобы создать контейнер ActiveX для любого из следующих типов приложений

1. [Контейнеры](../../mfc/containers.md)

1. [Визуальное редактирование](../../mfc/ole-mfc.md)

1. [Элементы управления ActiveX в MFC](../../mfc/mfc-activex-controls.md)

## <a name="see-also"></a>См. также

[Типы проектов Visual C++](../../ide/visual-cpp-project-types.md)
