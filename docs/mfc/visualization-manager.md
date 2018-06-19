---
title: Диспетчер визуализации | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Visualization Manager
ms.assetid: c9dd1365-27ac-42e5-8caa-1004525b4129
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40d16e1373d347b4a715cd6f073211796913bd21
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384219"
---
# <a name="visualization-manager"></a>Диспетчер визуализации
Диспетчер визуальных является объект, который управляет внешним видом всего приложения. Он действует как отдельный класс, можно поместить весь код отрисовки для вашего приложения. Библиотека MFC содержит несколько диспетчеров визуального представления. Также можно создать собственный Диспетчер визуальных, если вы хотите создать настраиваемое представление для вашего приложения. На следующих изображениях представлены того же приложения, при включении различных диспетчеров визуального представления:  
  
 ![MyApp, преобразованный CMFCVisualManagerWindows](../mfc/media/vmwindows.png "vmwindows")  
MyApp, который использует диспетчер visual преобразованный CMFCVisualManagerWindows  
  
 ![MyApp, преобразованный CMFCVisualManagerVS2005](../mfc/media/vmvs2005.png "vmvs2005")  
MyApp, который использует диспетчер visual преобразованный CMFCVisualManagerVS2005  
  
 ![MyApp, преобразованный CMFCVisualManagerOfficeXP](../mfc/media/vmofficexp.png "vmofficexp")  
MyApp, который использует диспетчер visual преобразованный CMFCVisualManagerOfficeXP  
  
 ![MyApp, преобразованный CMFCVisualManagerOffice2003](../mfc/media/vmoffice2003.png "vmoffice2003")  
MyApp, который использует диспетчер visual преобразованный CMFCVisualManagerOffice2003  
  
 ![MyApp, преобразованный CMFCVisualManagerOffice2007](../mfc/media/msoffice2007.png "msoffice2007")  
MyApp, который использует диспетчер visual преобразованный CMFCVisualManagerOffice2007  
  
 По умолчанию Диспетчер визуальных поддерживает код рисования для нескольких элементов графического пользовательского интерфейса. Чтобы предоставить элементы пользовательского интерфейса, необходимо переопределить связанные методы рисования visual диспетчера. Список этих методов см. в разделе [CMFCVisualManager класса](../mfc/reference/cmfcvisualmanager-class.md). Методы, которые можно переопределить, чтобы задать внешний вид, все методы, которые начинаются с `OnDraw`.  
  
 Приложение может иметь только одну `CMFCVisualManager` объекта. Чтобы получить указатель на диспетчер визуального представления для приложения, вызовите статическую функцию [CMFCVisualManager::GetInstance](../mfc/reference/cmfcvisualmanager-class.md#getinstance). Поскольку наследуют все диспетчеры visual `CMFCVisualManager`, `CMFCVisualManager::GetInstance` метод получить указатель на соответствующий наглядный диспетчер даже при создании пользовательского диспетчера visual.  
  
 Если вы хотите создать пользовательский диспетчер визуального представления, он должен быть производным от наглядный диспетчер, который уже существует. Класс по умолчанию, являются производными от `CMFCVisualManager`. Тем не менее если оно лучше похоже, применить к приложению можно использовать другой диспетчер visual. Например, если решено использовать `CMFCVisualManagerOffice2007` диспетчер визуального представления, но требуется только изменять вид разделители, можно создать пользовательский класс от `CMFCVisualManagerOffice2007`. В этом сценарии необходимо перезаписать только методы для рисования в качестве разделителей.  
  
 Существует два способа использовать Диспетчер визуальных конкретного приложения. Один способ — вызвать [CMFCVisualManager::SetDefaultManager](../mfc/reference/cmfcvisualmanager-class.md#setdefaultmanager) метод и передайте соответствующие наглядный диспетчер как параметр. В следующем примере кода показано, как использовать `CMFCVisualManagerVS2005` диспетчер визуального представления с помощью этого метода:  
  
```  
CMFCVisualManager::SetDefaultManager (RUNTIME_CLASS (CMFCVisualManagerVS2005));
```  
  
 Другой способ использовать Диспетчер визуальных приложения является создание его вручную. Затем приложение будет использовать этот новый диспетчер визуального представления подготовки к просмотру. Тем не менее поскольку может существовать только один `CMFCVisualManager` объекта каждого приложения, необходимо будет удалить текущий диспетчер visual, прежде чем создавать новый. В следующем примере `CMyVisualManager` представляет собой пользовательский диспетчер visual, производный от `CMFCVisualManager`. Следующий метод будет изменен, какой диспетчер визуального представления используется для отображения приложения, в зависимости от индекса:  
  
```  
void CMyApp::SetSkin (int index)  
{  
    if (CMFCVisualManager::GetInstance() != NULL)  
 {  
    delete CMFCVisualManager::GetInstance();

 }  
 
    switch (index)  
 {  
    case DEFAULT_STYLE: *// The following statement creates a new CMFCVisualManager  
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
 [Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)   
 [Класс CMFCVisualManager](../mfc/reference/cmfcvisualmanager-class.md)
