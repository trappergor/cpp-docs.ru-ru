---
title: Диспетчер визуализации
ms.date: 06/28/2018
helpviewer_keywords:
- Visualization Manager
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
ms.openlocfilehash: befff860f50677f9c70c0fbb6b45ac528c36e773
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50521376"
---
# <a name="visualization-manager"></a>Диспетчер визуализации

Наглядный диспетчер — это объект, который определяет отображение всего приложения. Он действует как отдельный класс, позволяющий поместить весь код рисования для вашего приложения. Библиотека MFC содержит несколько диспетчеров визуального представления. Можно также создать свои собственные наглядный диспетчер, если вы хотите создать пользовательское представление для вашего приложения. На рисунках ниже показаны того же приложения, когда включены различные диспетчеров визуального представления:

![MyApp, преобразованный CMFCVisualManagerWindows](../mfc/media/vmwindows.png "vmwindows") MyApp, который использует диспетчер visual CMFCVisualManagerWindows

![MyApp, преобразованный CMFCVisualManagerVS2005](../mfc/media/vmvs2005.png "vmvs2005") MyApp, который использует диспетчер visual CMFCVisualManagerVS2005

![MyApp, преобразованный CMFCVisualManagerOfficeXP](../mfc/media/vmofficexp.png "vmofficexp") MyApp, который использует диспетчер visual CMFCVisualManagerOfficeXP

![MyApp, преобразованный CMFCVisualManagerOffice2003](../mfc/media/vmoffice2003.png "vmoffice2003") MyApp, который использует диспетчер visual CMFCVisualManagerOffice2003

![MyApp, преобразованный CMFCVisualManagerOffice2007](../mfc/media/msoffice2007.png "msoffice2007") MyApp, который использует диспетчер visual CMFCVisualManagerOffice2007

По умолчанию наглядный диспетчер поддерживает код прорисовки для нескольких элементов графического пользовательского интерфейса. Чтобы предоставить элементы пользовательского интерфейса, необходимо переопределить соответствующие методы рисования visual диспетчера. Список этих методов, см. в разделе [класс CMFCVisualManager](../mfc/reference/cmfcvisualmanager-class.md). Методы, которые можно переопределить, чтобы задать внешний вид, все методы, которые начинаются с `OnDraw`.

Приложение может иметь только один `CMFCVisualManager` объекта. Чтобы получить указатель на диспетчер visual для приложения, вызовите статическую функцию [CMFCVisualManager::GetInstance](../mfc/reference/cmfcvisualmanager-class.md#getinstance). Так как все диспетчеров визуального представления является производным от `CMFCVisualManager`, `CMFCVisualManager::GetInstance` метод будет получить указатель на соответствующий наглядный диспетчер, даже при создании пользовательских наглядный диспетчер.

Если вы хотите создать пользовательские наглядный диспетчер, он должен быть производным от наглядный диспетчер, который уже существует. По умолчанию используется класс для наследования от `CMFCVisualManager`. Тем не менее можно использовать разные диспетчеры visual, если оно лучше похоже на то, что нужно для вашего приложения. Например, если решено использовать `CMFCVisualManagerOffice2007` наглядный диспетчер, но требуется только изменить вид разделители, можно создать пользовательский класс из `CMFCVisualManagerOffice2007`. В этом случае необходимо перезаписать только методы для рисования разделители.

Существует два возможных способа для использования определенных наглядный диспетчер для вашего приложения. Первый способ — вызвать [CMFCVisualManager::SetDefaultManager](../mfc/reference/cmfcvisualmanager-class.md#setdefaultmanager) метод и передать соответствующие наглядный диспетчер как параметр. В следующем примере кода показано, как использовать `CMFCVisualManagerVS2005` наглядный диспетчер, с помощью этого метода:

```cpp
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));
```

Другой способ использования наглядный диспетчер приложения является создание его вручную. Приложение будет использовать этот новый диспетчер visual для всех задач визуализации. Тем не менее поскольку может существовать только один `CMFCVisualManager` объекта каждого приложения, необходимо удалить текущий наглядный диспетчер, прежде чем создавать новый. В следующем примере `CMyVisualManager` является пользовательский наглядный диспетчер, который является производным от `CMFCVisualManager`. Следующий метод изменится какие наглядный диспетчер используется для отображения приложения, в зависимости от индекса:

```cpp
void CMyApp::SetSkin (int index)
{
    if (CMFCVisualManager::GetInstance() != NULL)
    {
        delete CMFCVisualManager::GetInstance();
    }

    switch (index)
    {
    case DEFAULT_STYLE:
        // The following statement creates a new CMFCVisualManager
        CMFCVisualManager::GetInstance();
        break;

    case CUSTOM_STYLE:
        new CMyVisualManager;
        break;

    default:
        CMFCVisualManager::GetInstance();
        break;
    }

    CMFCVisualManager::GetInstance()->RedrawAll();
}
```

## <a name="see-also"></a>См. также

[Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)<br/>
[Класс CMFCVisualManager](../mfc/reference/cmfcvisualmanager-class.md)
