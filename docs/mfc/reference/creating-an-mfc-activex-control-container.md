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
ms.openlocfilehash: 27f229a23595d4842a77409a3cedc7a57aa43e6c
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079426"
---
# <a name="creating-an-mfc-activex-control-container"></a>Создание контейнеров элементов управления MFC ActiveX

Контейнер элементов управления ActiveX — это родительская программа, предоставляющая среду для выполнения элемента управления ActiveX (прежнее название — OLE). Можно создать приложение, которое может содержать элементы управления ActiveX, с MFC или без него, но гораздо проще с MFC.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которую не следует использовать для новой разработки. Дополнительные сведения о современных технологиях, которые заменяют ActiveX, см. в разделе [элементы управления ActiveX](../activex-controls.md).

Создание программы контейнера MFC с помощью [мастера приложений MFC](../../mfc/reference/mfc-application-wizard.md) позволяет получить доступ ко многим функциям элементов управления ActiveX и автоматизации, реализованных классами MFC и ActiveX. Эти функции включают визуальное редактирование, автоматизацию, создание составных файлов и поддержку элементов управления. Параметры визуального редактирования мастера приложений MFC, которые будут поддерживаться родительской программой, включают создание контейнера, мини-сервера, полного сервера и программы, которая является контейнером и сервером.

- **Новое приложение MFC**. Чтобы создать новую программу MFC, включающую в себя автоматизацию, визуальное редактирование, составные файлы или поддержку элементов управления, используйте мастер приложений MFC и выберите соответствующие параметры автоматизации.

- **Существующее приложение MFC**. Если вы добавляете элемент управления в существующее приложение MFC, см. раздел [контейнеры элементов управления OLE: включение включения элемента управления OLE вручную](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md).

### <a name="to-create-an-activex-container-for-any-of-the-following-types-of-applications"></a>Создание контейнера ActiveX для любого из следующих типов приложений

1. [Контейнеры](../../mfc/containers.md)

1. [Визуальное редактирование](../../mfc/ole-mfc.md)

1. [Элементы управления ActiveX в MFC](../../mfc/mfc-activex-controls.md)

## <a name="see-also"></a>См. также:

[Типы проектов C++ в Visual Studio](../../build/reference/visual-cpp-project-types.md)
